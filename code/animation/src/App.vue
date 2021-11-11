<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Bir daha deniyorum"/>
</template>

<div id="app-3">
  <span v-if="seen">Now you see me</span>
</div>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
var app3 = new Vue({
  el: '#app-3',
  data: {
    seen: true
  }
})

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
