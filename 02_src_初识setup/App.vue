<template>
  <h1>我是app组件</h1>
  <h1>我叫{{ name }}, {{ age }}岁</h1>
  <button @click="sayHello">hello!!</button>
</template>

<script>
export default {
  name: 'App',
  setup() {
    let name = '张三';
    let age = 18;

    function sayHello() {
      alert(`My name is ${name},and ${age}`);
    }

    //返回一个对象
    return {
      name,
      age,
      sayHello
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
