<template>
  <h1>Information</h1>
  <h2>name: {{ person.name }}</h2>
  <h2>age : {{ person.age }}</h2>
  <h3>job type : {{ person.job.type }}</h3>
  <h3>job salary : {{ person.job.salary }}</h3>
  <h3>测试的数据c : {{ person.job.a.b.c }}</h3>
  <h3>爱好: {{ person.hobby }}</h3>
  <button @click="changeInfo">Change Info</button>
</template>

<script>
import {reactive} from 'vue'

export default {
  name: 'App',
  setup(){
    let person = reactive({
      name: 'wanglin',
      age: 18,
      job: {
        type: '前端工程师',
        salary: '30k',
        a: {
          b: {
            c: 666
          }
        }
      },
      hobby: ['抽烟', '喝酒', '烫头']
    })

    function changeInfo(){
      person.name = 'ponyo'
      person.age = 20
      person.job.type = '人工智能工程师'
      person.job.salary = '50k'
      person.job.a.b.c = 9999
      person.hobby[0] = '学习'
    }

    return {
      person,
      changeInfo      
    }
  }
}
</script>
