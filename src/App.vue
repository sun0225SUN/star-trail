<script setup>
import StarTrails from './components/StarTrails.vue'

window.addEventListener('scroll', () => {
  const bg = document.getElementById('background')
  const scrollTop = window.scrollY
  if (scrollTop > 0.7 * window.innerHeight)
    bg.classList.add('fixed')
  else
    bg.classList.remove('fixed')
})
</script>

<template>
  <div id="background" absolute wh-full left-0 top-0>
    <!-- 渐变 -->
    <div to-black-500 absolute h-80vh w-full bottom--30vh left-0 from-black bg-gradient-to-t />
    <!-- 星轨 -->
    <StarTrails />
    <!-- 拖底 -->
    <div bg-black h-45vh />
  </div>

  <main bg-black bg-transparent absolute w-full top-0>
    <div absolute top-70vh>
      <div ml-15vw>
        <div text-10 text-white font-bold tracking-widest>
          你所热爱的<br>
          就是你的生活
        </div>
        <div flex items-center>
          <div mr-4 flex gap-2>
            <div bg-red rounded-full h-3 w-3 />
            <div bg-yellow rounded-full h-3 w-3 />
            <div bg-green rounded-full h-3 w-3 />
          </div>
          <div text-4 text-white>
            小孙同学祝您今天快乐
          </div>
        </div>
      </div>
      <div ml-50vw mt-30>
        <h1 text-white>
          测试文本，占位
        </h1>
        <h1 text-white>
          测试文本，占位
        </h1>
        <h1 text-white>
          测试文本，占位
        </h1>
        <h1 text-white>
          测试文本，占位
        </h1>
        <h1 text-white>
          测试文本，占位
        </h1>
        <h1 text-white>
          测试文本，占位
        </h1>
        <h1 text-white>
          测试文本，占位
        </h1>
        <h1 text-white>
          测试文本，占位
        </h1>
        <h1 text-white>
          测试文本，占位
        </h1>
        <h1 text-white>
          测试文本，占位
        </h1>
        <h1 text-white>
          测试文本，占位
        </h1>
        <h1 text-white>
          测试文本，占位
        </h1>
        <h1 text-white>
          测试文本，占位
        </h1>
        <h1 text-white>
          测试文本，占位
        </h1>
        <h1 text-white>
          测试文本，占位
        </h1>
        <h1 text-white>
          测试文本，占位
        </h1>
        <h1 text-white>
          测试文本，占位
        </h1>
        <h1 text-white>
          测试文本，占位
        </h1>
        <h1 text-white>
          测试文本，占位
        </h1>
        <h1 text-white>
          测试文本，占位
        </h1>
        <h1 text-white>
          测试文本，占位
        </h1>
        <h1 text-white>
          测试文本，占位
        </h1>
      </div>
    </div>
  </main>

  <nav absolute fixed bottom-0 left-0>
    <div>
      <div mb-8 ml-2 flex-col gap-8 justify-center items-center>
        <div text-3 text-white wv>
          <a class="text-white" opacity-75 href="https://blog.sunguoqi.com" tracking-widest>博 客</a>
        </div>
        <div text-3 text-white wv>
          <a class="text-white" opacity-75 href="https://camera.sunguoqi.com" tracking-widest>相 册</a>
        </div>
        <div text-3 text-white wv>
          <a class="text-white" opacity-75 href="https://bicycling.sunguoqi.com" tracking-widest>运 动</a>
        </div>
        <div text-3 text-white wv>
          <a class="text-white" opacity-75 href="https://blog.sunguoqi.com/comments" tracking-widest>留 言 板</a>
        </div>
      </div>
    </div>
  </nav>
</template>

<style lang="scss" scoped>
#background.fixed {
  position: fixed;
  top: -70%;
}
</style>
