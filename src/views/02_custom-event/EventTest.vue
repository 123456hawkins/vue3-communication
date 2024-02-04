<template>
  <div>
    <h1>事件</h1>
    <!-- 原生DOM事件 -->
    <pre @click="handler">
      大江东去浪淘尽,千古分流人物
    </pre>
    <button @click="handler1(1, 2, 3, $event)">点击我传递多个参数</button>
    <hr />
    <!--
        vue2框架当中:这种写法自定义事件,可以通过.native修饰符变为原生DOM事件
        vue3框架下面写法其实即为原生DOM事件

        vue3:原生的DOM事件不管是放在标签身上、组件标签身上都是原生DOM事件
      -->
    <Event1 @click="handler2"></Event1>
    <hr />
    <!-- 绑定自定义事件xxx:实现子组件给父组件传递数据 -->
    <!-- 原生dom事件(比如click)在子组件，只要定义了就会变成自定义事件 -->
    <Event2 @xxx="handler3" @click="handler4"></Event2>
  </div>
</template>

<script setup lang="ts">
//引入子组件
import Event1 from './Event1.vue'
//引入子组件
import Event2 from './Event2.vue'
//事件回调--1 原生的dom事件会向事件注入默认回调event
const handler = (event) => {
  //event即为事件对象 包含鼠标位置，
  console.log('handler event Obj:', event)
}
//事件回调--2
const handler1 = (a, b, c, $event) => {
  console.log('handler1', a, b, c, $event)
}
//事件回调---3
const handler2 = (event) => {
  console.log('handler2', 123, event)
}
//事件回调---4
const handler3 = (param1, param2) => {
  console.log('handler3', param1, param2)
}
//事件回调--5
const handler4 = (param1, param2) => {
  console.log('handler4', param1, param2)
}
</script>

<style scoped></style>
