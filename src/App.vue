<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App Sun Japan"/>
  <HeaderStudy/>
  <ToDoStudy/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import HeaderStudy from './components/HeaderStudy.vue'
import ToDoStudy from './components/ToDoStudy.vue'

export default {
  name: 'App',
  components: {
    HelloWorld, HeaderStudy, ToDoStudy
  }
}
</script>

<style>
#app {
   font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-top: 60px; 
}
</style>
