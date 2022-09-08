<template>
  <div class="header_container ">
    <div>
        <img src="../assets/spotify_logo_icon_186877.png" alt="">
    </div>
    <div>
            <select class="form-select"  >
                <option value="">Seleziona un genere</option>
                <option>1</option>
            </select>
        </div>
  </div>
</template>

<script>
export default {

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
        div{
            // text-align: left;
        }
        img{
            width: 70px;
            aspect-ratio: 1;
        }
    }

</style>