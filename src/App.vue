<template>
  <div id="app">
    <HeaderComponent @genreChangeFtn="getGenre" @authorChangeFtn="getAuthor"/>
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <CardContainer :selectedGenre="genreProp" />
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import CardContainer from './components/CardContainer.vue';
import HeaderComponent from './components/HeaderComponent.vue'

export default {
  name: 'App',
  data(){
    return {
      genreProp: '',
      authorProp: ''
    }
  },
  components: {
    // HelloWorld,
    CardContainer,
    HeaderComponent
  },
  methods: {
    getGenre(data) {
      console.log("ascolto l'evento", data)
      this.genreProp = data
    }
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
