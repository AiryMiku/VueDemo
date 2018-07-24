<template>
  <div id="app">
    <img src="./assets/logo.png">
    <router-view/>
    <!--路由，局部刷新-->
  </div>
</template>

<script>
import Hello from './components/HelloWorld'
import Test from './components/Test'
export default {
  name: 'App',
  components: {
    Hello,
    Test
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
