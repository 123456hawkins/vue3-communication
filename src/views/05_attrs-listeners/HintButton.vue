<template>
  <div :title="title">
    <!-- 父组件传过来的属性全部赋给el-button -->
    <el-button :="$attrs"></el-button>
  </div>
</template>

<script setup lang="ts">
//引入useAttrs方法:获取组件标签身上属性与事件
import { useAttrs } from 'vue'
//此方法执行会返回一个对象
let $attrs = useAttrs()
console.log('attrs Obj', $attrs)

//万一用props接受title
// let props = defineProps(['title'])
//props与useAttrs方法都可以获取父组件传递过来的属性与属性值
//但是props接受了useAttrs方法就获取不到了
console.log($attrs)
</script>

<style scoped></style>
