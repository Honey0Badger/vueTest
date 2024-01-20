<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>
  <Hello msg="terminator"
  foto="https://yandex.ru/images/search?pos=0&from=tabbar&img_url=https%3A%2F%2Fa.d-cd.net%2FlgAAAgIsZeA-1920.jpg&text=terminator+photo&rpt=simage&lr=213"/>
  <hello descr="terminator"/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Hello from './components/Hello.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    Hello
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
