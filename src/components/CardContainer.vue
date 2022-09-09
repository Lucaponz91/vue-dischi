<template>
    <div class="card_container">
        <CardComponent v-for="(disc, index) in filteredDiscs" :key="index"
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
        },
        selectedAuthor:{
            type: String,
            default: ''
        }
    },
    data(){ 
        return {
            listDiscs: [],
            
            
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
        filteredDiscs() {
        return this.listDiscs.filter((el) => {
          const genre = el.genre;
          console.log(genre)
          const find = this.selectedGenre;
          const author = el.author.toLowerCase();
          console.log(author)
          const findAuthor = this.selectedAuthor.toLowerCase();
          if (genre.includes(find) && author.includes(findAuthor)){
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