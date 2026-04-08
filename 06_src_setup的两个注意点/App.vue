<template>
  <Demo @hello="showHelloMsg" msg="你好" school="西华师大">
    <template v-slot:qwe>
      插槽1
    </template>
    <template v-slot:asd>
      插槽2
    </template>
  </Demo>
</template>

<script>
import Demo from "./components/Demo";

export default {
  name: 'App',
  components: {Demo},
  setup() {
    return {
      showHelloMsg(value) {
        alert(`你好啊，你触发了hello事件，我收到的参数是:,${value}`);
      }
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
