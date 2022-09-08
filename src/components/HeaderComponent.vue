<template>
  <div class="header_container ">
    <div>
        <img src="../assets/spotify_logo_icon_186877.png" alt="">
    </div>
    <div>
            <select class="form-select"  v-model="selectedGenre" @change="$emit('selectedGenre', selectedGenre)">
                <option value="">Seleziona un genere</option>
                <option value="Rock">Rock</option>
                <option value="Pop">Pop</option>
                <option value="Jazz">Jazz</option>
                <option value="Metal">Metal</option>
            </select>
            
        </div>
  </div>
</template>

<script>
export default {
    data(){
        return{
            selectedGenre: ''
        }

    }

}
</script>

<style lang="scss" scoped>
    .header_container{
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: space-between;
        height: 70px;
        background-color: #2E3A46;
        
        img{
            width: 70px;
            aspect-ratio: 1;
        }
    }

</style>