<template>
  <div class="child2">
    <h1>同时绑定多个v-model</h1>
    <button @click="handler1">pageNo{{ pageNo }}</button>
    <button @click="handler2">pageSize{{ pageSize }}</button>
  </div>
</template>

<script setup lang="ts">
const props = defineProps(['pageNo', 'pageSize'])
const $emit = defineEmits(['update:pageNo', 'update:pageSize'])
const handler1 = () => {
  $emit('update:pageNo', props.pageNo + 4)
}
const handler2 = () => {
  $emit('update:pageSize', props.pageSize + 6)
}
</script>

<style scoped>
.child2 {
  width: 300px;
  height: 300px;
  background: hotpink;
}
</style>
