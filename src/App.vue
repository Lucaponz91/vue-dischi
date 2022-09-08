<template>
  <div id="app">
    <HeaderComponent/>
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <CardContainer/>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import CardContainer from './components/CardContainer.vue';
import HeaderComponent from './components/HeaderComponent.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld,
    CardContainer,
    HeaderComponent
}
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
