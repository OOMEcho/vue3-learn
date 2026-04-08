<template>
  <h1>我是app组件</h1>
  <h1>我叫{{ person.name }}, {{ person.age }}岁</h1>
  <button @click="test">测试触发一次demo的自定义事件</button>
</template>

<script>
import {reactive} from 'vue';

export default {
  name: 'Demo',
  props: ['msg', 'school'],
  emits: ['hello'],
  setup(props, context) {
    console.log('---setup---props:', props); //props: 外部给组件丢的参数 => 响应式(Proxy实例)
    console.log('---setup---context:', context); // 上下文

    // console.log(---setup---context.attrs:, context.attrs); 相当于vue2中的$attrs
    // console.log(---setup---context.emit:, context.emit); 触发事件的方法
    // console.log(---setup---context.slots:,context.slots); 插槽

    let person = reactive({
      name: '张三',
      age: 18,
    });

    return {
      person,
      test() {
        context.emit('hello', 666);
      }
    }
  }
}
</script>

<style>
</style>
