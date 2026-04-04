<template>
  <h1>我是app组件</h1>
  <h1>我叫{{ person.name }}, {{ person.age }}岁</h1>
  <h3>职位:{{ person.type }}</h3>
  <h3>薪水:{{ person.salary }}</h3>
  <h3>爱好:{{ person.hobbies }}</h3>
  <h4>测试的数据c:{{ person.a.b.c }}</h4>
  <button @click="changeInfo">修改人的信息</button>
</template>

<script>
import { reactive } from 'vue';
export default {
  name: 'App',
  setup(){
    //ref实现响应式(基本类型)也是采用Object.definedProperty()来实现的 getter和setter
    //ref实现响应式(对象类型)也是采用Proxy来实现(proxy) 这里如果就算是用ref也是借助了reactive
    let person = reactive({
      name: '张三',
      age: 18,
      type: '前端工程师',
      salary: '30k',
      hobbies: ['打游戏', '抽烟'],
      a:{
        b:{
          c: 666
        }
      }
    });


    function changeInfo(){
      person.name = '李四';
      person.age = 42;
      person.type = 'UI工程师';
      person.salary = '40k';
      //测试reactive能否监测深层次变化
      person.a.b.c = 100;
      person.hobbies[0] = '打篮球';
    }

    return {
      person,
      changeInfo
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
