<template>
  <div >
  <!-- <b-card 
    :title="title"
    :img-src="imgUrl"
    img-alt="Image"
    img-top
    tag="article"
    style="max-width: 20rem;"
    class="mb-2 card"
  >
    <h5>{{author}}</h5>
    <h5>{{year}}</h5>

    
  </b-card> -->
  <div class="card " style="width: 18rem;">
  <img class="card-img-top" :src="imgUrl" alt="Card image cap">
  <div class="card-body">
    <h5 class="card-title">{{title}}</h5>
    <h5>{{author}}</h5>
    <h5>{{year}}</h5>
  </div>
</div>
</div>


</template>

<script>
export default {
    props: {
        title: String,
        author: String,
        year: String,
        imgUrl: String
    },
    

}
</script>

<style lang="scss" scoped>
    .card{
        background-color: #2E3A46;
        max-width: 200px;
        height: 300px;
        display: flex;
        align-items: center;
        margin-bottom: 10px;
        .card-title{
            color: white;
        }
        h5{
            color: lightgray;
        }
        img{
            height: 160px;
            width: 160px;
        }
    }

</style>