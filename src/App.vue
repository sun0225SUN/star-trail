<script setup>
import StarTrails from './components/StarTrails.vue'
</script>

<template>
  <div absolute wh-full left-0 top-0>
    <!-- 渐变 -->
    <div to-black-500 absolute h-80vh w-full class="bottom-[-30vh]" left-0 from-black bg-gradient-to-t />
    <!-- 星轨 -->
    <StarTrails />
    <!-- 拖底 -->
    <div bg-black h-45vh />
  </div>

  <div bg-black bg-transparent f-c-c absolute h-100vh w-full top-0>
    <div text-white>
      <div>
        正在开发中...
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
</style>
