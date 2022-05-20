<template>
<div class="album--wrap d-flex justify-content-center align-items-center my-5  ">

  <section class="album--wrap__list row w-75 row-cols-5 py-3">
    <AlbumCard 
    v-for="(album, index) in albumsArray" 
    :key ="index" 
    :AlbumItem ="album"
    />
  
  </section>
</div>
</template>

<script>
import AlbumCard from "./AlbumCard.vue"
import axios from "axios";

export default {
  name: "AlbumList",

  components: {
    AlbumCard,
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

.album--wrap {

    &__list{

    background-color: $background-color-album-list;
    }

}


</style>
