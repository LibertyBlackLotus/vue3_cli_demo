<template>
  <h1>Information</h1>
  <h2>
    name: {{ name }}
  </h2>
  <h2>
    age : {{ age }}
  </h2>
  <button @click="sayHello">say</button>
</template>

<script>
import { h } from 'vue'

export default {
  name: 'App',
  setup(){
    let name = 'wanglin'
    let age = 18

    function sayHello(){
      alert(`我是${name}, 我${age}岁了，你好啊！`)
    }

    // return {
    //   name,
    //   age,
    //   sayHello
    // }

    //返回渲染函数
    return () => h('h1', 'hello')
  }
}
</script>
