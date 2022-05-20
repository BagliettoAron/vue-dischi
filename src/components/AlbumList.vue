<template>
  <div class="albumList">
    <div class="selection">
      <SearchElement @scelta='selectedOption($event)'/>
    </div>
    <div class="container">
      <div class="row text-center row-cols-5 m-5">
        <AlbumCard
          v-for="(album, index) in albumsArray"
          :key="index"
          :AlbumItem="album"
        />
      </div>
    
    </div>
  </div>
</template>

<script>
import AlbumCard from "./AlbumCard.vue";
import SearchElement from "./SearchElement.vue";
import axios from "axios";

export default {
  name: "AlbumList",

  components: {
    AlbumCard,
    SearchElement
  },

  methods: {
    selectedOption (genere) {

      console.log('selezionato', genere);
    }
  },

  data: function () {
    return {
      albumsArray: [],
    }; 
  },

  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((resp) => {
        this.albumsArray = resp.data.response;
      });
  },
};
</script>

<style lang="scss" scoped>
@import "../style/variables.scss";
@import "../style/common.scss";

.albumList{

    background-color: $background-color-album-list;


}
</style>
