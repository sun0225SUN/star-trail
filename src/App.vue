<script setup>
import { onMounted, reactive } from 'vue'
import StarTrails from './components/StarTrails.vue'

const data = reactive({
  navLinks: [{
    name: '博 客',
    link: 'https://blog.sunguoqi.com',
  }, {
    name: '相 册',
    link: 'https://camera.sunguoqi.com',
  }, {
    name: '运 动',
    link: 'https://bicycling.sunguoqi.com',
  }, {
    name: '留 言',
    link: 'https://blog.sunguoqi.com/comments',
  }],

  myProjects: [{
    name: 'Home',
    description: '个人简介、主页、引导页',
    link: 'https://github.com/sun0225SUN/home',
  }, {
    name: 'Blog',
    description: '个人博客，学习&随笔',
    link: 'https://github.com/sun0225SUN/blog',
  }, {
    name: 'Brain',
    description: '知识库、第二大脑',
    link: 'https://github.com/sun0225SUN/brain',
  }, {
    name: 'Camera',
    description: '摄影相册',
    link: 'https://github.com/sun0225SUN/camera',
  }, {
    name: 'Camera Tools',
    description: '摄影工具箱',
    link: 'https://github.com/sun0225SUN/camera-tools',
  }, {
    name: 'Bicycling',
    description: '骑行主页',
    link: 'https://github.com/sun0225SUN/bicycling',
  }, {
    name: 'Life-Map',
    description: '人生地图、点亮足迹',
    link: 'https://github.com/sun0225SUN/life-map',
  }, {
    name: 'Coder',
    description: '闪闪发光的程序们',
    link: 'https://github.com/sun0225SUN/coder',
  }, {
    name: 'Starter',
    description: '前端项目起手架模版',
    link: 'https://github.com/sun0225SUN/starter',
  }],

  socialLinks: [{
    icon: '<i i-ant-design-github-outlined />',
    link: 'https://github.com/sun0225SUN',
    label: 'Github',
  }, {
    icon: '<i i-ant-design-x-outlined />',
    link: 'https://twitter.com/sun0225SUN',
    label: 'Twitter',
  }, {
    icon: '<i i-ant-design-youtube-outlined />',
    link: 'https://youtube.com/@sun0225SUN',
    label: 'YouTube',
  }, {
    icon: '<i i-ant-design-bilibili-outlined />',
    link: 'https://space.bilibili.com/448488855/',
    label: 'Bilibili',
  }],
})

onMounted(() => {
  // 背景固定
  window.addEventListener('scroll', () => {
    const bg = document.getElementById('background')
    const scrollTop = window.scrollY
    if (scrollTop > 0.7 * window.innerHeight)
      bg.classList.add('fixed')
    else
      bg.classList.remove('fixed')
  })
})
</script>

<template>
  <!-- 导航 -->
  <nav absolute fixed bottom-4 left-4 z-20>
    <div v-for="(item, index) in data.navLinks" :key="index" my-6 text-3 text-white wv>
      <a :href="item.link" opacity-75 text-white tracking-widest hover:opacity-100>
        {{ item.name }}
      </a>
    </div>
  </nav>

  <!-- 主体 -->
  <main bg-transparent absolute w-full top-72vh z-10>
    <!-- 大标题 -->
    <section ml-15vw absolute>
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
        <div text-4 text-white tracking-widest>
          小孙同学祝您今天快乐
        </div>
      </div>
    </section>
    <!-- 个人简介 -->
    <section mx-9vw mt-110>
      <!-- 关于我 -->
      <div text-bold mb-4 ml-10 text-8 text-white>
        About Me
      </div>
      <div mx-10 mb-10 flex justify-between>
        <div class="text-white/80">
          <p leading-10>
            嗨，你好，我是小孙同学。
          </p>
          <p leading-10>
            热爱编程、摄影、读书、旅行。
          </p>
          <p leading-10>
            热爱计算机科学和 IT 互联网事业，希望能成为一名优秀的开发者。
          </p>
          <p leading-10>
            我们正在让这个世界变得更加美好，通过代码的重复使用和延展构建完美体系。
          </p>
          <p leading-10>
            We're making the world a better place. Through constructing elegant hierarchies for maximum code reuse and extensibility.
          </p>
        </div>
        <div>
          <img hidden rounded-full w-25 md:block src="https://blog.sunguoqi.com/images/avatar.jpg" alt="avatar">
        </div>
      </div>

      <!-- 我的技能 -->
      <!-- <div text-bold mb-2 ml-10 text-8 text-white>
          My Skills
        </div> -->

      <!-- 我的项目 -->
      <div text-bold mb-2 ml-10 text-8 text-white>
        Projects
      </div>
      <div mb-10 flex flex-wrap justify-between>
        <div v-for="(item, index) in data.myProjects" :key="index" mx-10 my-4 class="basis-3/4 md:basis-1/6">
          <a :href="item.link">
            <div p-2 class="bg-white/5 hover:bg-white/10" rounded-lg shadow-md flex-col backdrop-blur-3xl backdrop-opacity-60 hover:skew-y-1 hover:backdrop-opacity-100>
              <div text-bold opacity-75 text-white>
                {{ item.name }}
              </div>
              <div mt-1 opacity-50 text-3 text-white>
                {{ item.description }}
              </div>
            </div>
          </a>
        </div>
      </div>

      <!-- 社交链接 -->
      <div text-bold mb-2 ml-10 text-8 text-white>
        Find Me
      </div>
      <div flex flex-wrap justify-between>
        <div v-for="(item, index) in data.socialLinks" :key="index" mx-10 my-4 class="basis-1/6">
          <a p-2 class="bg-white/5 hover:bg-white/10" rounded-lg shadow-md flex-col justify-between items-center backdrop-blur-3xl backdrop-opacity-60 hover:skew-y-1 hover:backdrop-opacity-100 :href="item.link">
            <div mb-1 text-white f-c-c v-html="item.icon" />
            <div text-bold opacity-75 text-white>{{ item.label }}</div>
          </a>
        </div>
      </div>
    </section>

    <!-- 底部 -->
    <footer>
      <div mt-100 f-c-c class="text-white/60" hover:skew-y-1>
        <i i-ant-design-environment-outlined mr-1 />
        <p>路虽远行则将至，事虽难做则必成</p>
        <i i-ant-design-environment-outlined ml-1 />
      </div>
      <div mt-2 f-c-c class="text-white/60" gap-4>
        <div>皖 ICP 备 2021010058 号</div>
        <div>© 2024 小孙同学</div>
      </div>
    </footer>
  </main>

  <!-- 背景 -->
  <div id="background" absolute wh-full left-0 top-0 z-0>
    <!-- 渐变阴影 -->
    <div to-black-500 absolute h-80vh w-full bottom--30vh left-0 from-black bg-gradient-to-t />
    <!-- 星轨背景 -->
    <StarTrails pb-45vh bg-black />
  </div>
</template>

<style lang="scss" scoped>
#background.fixed {
  position: fixed;
  top: -70%;
}
</style>
