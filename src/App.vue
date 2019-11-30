<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <HelloWorld msg="Welcome to Your Vue.js App" :realNum="num" :clientWidth="clientWidth"/>
    <!-- <countTo :startVal='startVal' :endVal='endVal' :duration='3000'></countTo> -->
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import countTo from 'vue-count-to';

export default {
  name: 'app',
  components: {
    HelloWorld,
    countTo
  },
  data(){
    return{
      startVal: 0,
        endVal: 201798765,
        num:[9,8,7,1],
        clientWidth:1990
    }
  },
  created() {
    this.clientWidth = document.body.clientWidth
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
