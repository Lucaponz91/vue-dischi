<template>
  <div class="header_container">
    <div>
      <img src="../assets/spotify_logo_icon_186877.png" alt="" />
    </div>
    <div class="selects_container">
      <select
        class="form-select"
        v-model="selectedGenre"
        @change="$emit('selectedGenre', selectedGenre)"
      >
        <option value="">Seleziona un genere</option>
        <option value="Rock">Rock</option>
        <option value="Pop">Pop</option>
        <option value="Jazz">Jazz</option>
        <option value="Metal">Metal</option>
      </select>
      <select
        v-model="selectedAuthor"
        @change="$emit('authorChangeFtn', selectedAuthor)"
      >
        <option value="">Seleziona un autore</option>
        <option value="bonjovi">Bon Jovi</option>
        <option value="queen">Queen</option>
        <option value="sting">Sting</option>
        <option value="stevegaddband">Steve Gadd Band</option>
        <option value="ironmaiden">Iron Maiden</option>
        <option value="ericclapton">Eric Clapton</option>
        <option value="deeppurple">Deep Purple</option>
        <option value="metallica">Metallica</option>
        <option value="daveweckl">Dave Weckl</option>
        <option value="michaeljacjson">Michael Jacjson</option>
      </select>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selectedGenre: "",
    };
  },
};
</script>

<style lang="scss" scoped>
.header_container {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  height: 70px;
  background-color: #2e3a46;

  img {
    width: 70px;
    aspect-ratio: 1;
  }
}
.selects_container{
  display: flex;
  flex-direction: row;
}
</style>