<template>
  <div id="app">
    <!-- BEGIN -->
    <!-- <HelloPrince></HelloPrince> -->
    <recived></recived>
    <!-- END -->
  </div>
</template>

<script>
// import HelloPrince from './components/HttpRequest.vue'
import recived from './components/HttpRequest.vue'


export default {
  name: 'app',
  components:{
    recived
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
