<template>
  <div >
  <b-card v-for="(discs, index) in listDiscs" :key="index"
    :title=discs.title
    :img-src=discs.poster
    img-alt="Image"
    img-top
    tag="article"
    style="max-width: 20rem;"
    class="mb-2"
  >
    <h5>{{discs.author}}</h5>
    <h5>{{discs.year}}</h5>

    
  </b-card>
  <!-- {{listDiscs}} -->
</div>

</template>

<script>
    import axios from 'axios'
export default {
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
            
    }

}
</script>

<style lang="scss" scoped>

</style>