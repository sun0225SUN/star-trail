<script setup>
const props = defineProps({
  msg: String,
})
</script>

<template>
  <div>Hello {{ props.msg }}!</div>
</template>

<style lang="scss" scoped>

</style>
