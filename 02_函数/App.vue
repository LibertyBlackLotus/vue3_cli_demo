<template>
  <h1>Information</h1>
  <h2>name: {{ name }}</h2>
  <h2>age : {{ age }}</h2>
  <h3>job type : {{ job.type }}</h3>
  <h3>job salary : {{ job.salary }}</h3>
  <button @click="changeInfo">Change Info</button>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'App',
  setup(){
    let name = ref('wanglin')
    let age = ref(18)
    let job = ref({
      type: '前端工程师',
      salary: '30k'
    })

    function changeInfo(){
      console.log(name) //name 为RefIml引用实例对象
      name.value = 'ponyo'
      age.value = 20
      job.value.type = '人工智能工程师',
      job.value.salary = '50k'
    }

    return {
      name,
      age,
      changeInfo,
      job
    }
  }
}
</script>
