<template>
    <div class="card_container">
        <CardComponent v-for="(disc, index) in filteredByGenre" :key="index"
        :imgUrl = "disc.poster"
        :author = "disc.author"
        :year = "disc.year"
        :title = "disc.title"
        class=""/>
    </div>
</template>

<script>
import CardComponent from './CardComponent.vue';
import axios from 'axios' ;
export default {
    components: { CardComponent, },
    props: {
        selectedGenre:  {
            type: String,
            default: ''
        }
    },
    data(){ 
        return {
            listDiscs: [],
            listGenres: [],
            
        }
    },
    created(){
        axios
            .get('https://flynn.boolean.careers/exercises/api/array/music')
            .then((res) =>{
                console.log(res.data);
                this.listDiscs = res.data.response;
                
            })
            .catch((err)=>{
                console.log("Errore!", err);
            })
            .finally(()=>{
                console.log("finito")
            })
    },
    computed:{
        filteredByGenre() {
        return this.listDiscs.filter((el) => {
          const genre = el.genre;
          console.log(genre)
          const find = this.selectedGenre
          if (genre.includes(find)){
            return true
          }
          return false
        });
      }
    }
    }
</script>


<style lang="scss" scoped>
    .card_container{
        // display: flex;
        // flex-wrap: wrap;
        background-color: #1E2D3B;
        display: grid;
        grid-template-columns: repeat(5, 1fr);
        padding: 20px;

    }

</style>