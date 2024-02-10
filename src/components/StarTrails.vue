<script setup>
import { onMounted } from 'vue'

onMounted(() => {
  // 创建两个 canvas 元素，show 用于显示，help 作为辅助
  const help = document.createElement('canvas')
  const show = document.getElementById('trails')

  // 声明两个变量 showWidth 和 showHeight，用于存储显示区域的宽度和高度
  let showWidth, showHeight

  // 让两个 canvas 的宽高与显示区域的宽高一致
  show.width = help.width = showWidth = show.offsetWidth
  show.height = help.height = showHeight = show.offsetHeight

  const longSide = Math.max(showWidth, showHeight)
  // 使用长边构造成一个大点的正方形
  help.width = longSide * 2.6
  help.height = longSide * 2.6

  // 获取上下文
  const showContext = show.getContext('2d')
  const helpContext = help.getContext('2d')

  // 设置显示区域背景色
  showContext.fillStyle = 'rgba(0,0,0,1)'
  showContext.fillRect(0, 0, showWidth, showHeight)

  // 创建随机颜色随机位置的星星
  function rand(Min, Max) {
    return Min + Math.round(Math.random() * (Max - Min))
  }

  // 随机颜色（指定范围）
  function randomColor() {
    const r = rand(120, 255)
    const g = rand(120, 255)
    const b = rand(120, 255)
    const a = rand(30, 100) / 100
    return `rgba(${r},${g},${b},${a})`
  }

  // 星星数组
  const stars = []

  // 创建每个星星的属性
  function createStar() {
    return {
      x: rand(-help.width, help.width),
      y: rand(-help.height, help.height),
      size: 1.2,
      color: randomColor(),
    }
  }

  // 绘制星星实例
  function drawStar() {
    let count = stars.length
    while (count--) {
      const star = stars[count]
      helpContext.beginPath()
      helpContext.arc(star.x, star.y, star.size, 0, Math.PI * 2, true)
      helpContext.fillStyle = star.color
      helpContext.closePath()
      helpContext.fill()
    }
  }

  // 计时
  let drawTimes = 0
  // 循环
  function loop() {
    // 开始绘制
    showContext.drawImage(help, -help.width / 2, -help.height / 2)

    drawTimes++

    if (drawTimes > 200 && drawTimes % 8 === 0) {
      showContext.fillStyle = 'rgba(0,0,0,.04)'
      showContext.fillRect(-(longSide * 3), -(longSide * 3), longSide * 6, longSide * 6)
    }
    // 旋转
    showContext.rotate(0.025 * Math.PI / 180)
  }

  let count = 18000

  while (count--)
    stars.push(createStar())

  drawStar()

  // 根据比例调整圆心
  if (showWidth < showHeight)
    showContext.translate(showWidth, showHeight)
  else
    showContext.translate(showWidth, 0)

  function animate() {
    window.requestAnimationFrame(animate)
    loop()
  }

  animate()

  // 监听浏览器窗口变化，变化则重新执行animate函数
  window.addEventListener('resize', () => {
    showWidth = show.offsetWidth
    showHeight = show.offsetHeight
    show.width = showWidth
    show.height = showHeight
    showContext.fillStyle = 'rgba(0,0,0,1)'
    showContext.fillRect(0, 0, showWidth, showHeight)
  })
})
</script>

<template>
  <div h-130vh>
    <canvas id="trails" wh-full />
  </div>
</template>

<style lang="scss" scoped></style>
