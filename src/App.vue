<script setup>
import MyComponent from './components/MyComponent.vue'
</script>

<template>
  <div class="flex flex-col h-[100vh] justify-center items-center">
    <MyComponent msg="Vue" />
    <div
      text="44px"
      color="blue"
    >
      Unocss
    </div>
    <a-button type="primary">
      Ant-Design-vue
    </a-button>
    <div class="flex h-[60px] justify-between items-center">
      <RouterLink to="/" class="w-[80px]">
        <div class="text-center">
          Home
        </div>
      </RouterLink>
      <RouterLink to="/about" class="w-[80px]">
        <div class="text-center">
          About
        </div>
      </RouterLink>
    </div>

    <RouterView />
  </div>
</template>

<style lang="scss" scoped>
</style>
