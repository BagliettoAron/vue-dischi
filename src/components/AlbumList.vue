<template>
  <div class="albumList">
    <div class="selection">
      <SearchElement @selected='selectedOption($event)'/>
    </div>
  <div class="container d-flex justify-content-center align-content-center p-5">
    <div class="container__list row w-75 text-center margin-auto row-cols-5 px-5">
      <AlbumCard
        v-for="(album, index) in albumsArray"
        :key="index"
        :AlbumItem="album"
      />
    </div>
  
  </div>
    class="album--wrap d-flex justify-content-center align-items-center my-5"
  >
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
    selectedOption () {

      console.log('selezionato');
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

  .album--wrap {
    &__list {
    }
  }
}
</style>
