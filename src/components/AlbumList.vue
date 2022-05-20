<template>
  <section class="album-list row w-75 row-cols-5 ">
    <AlbumCard />
    <AlbumCard />
    <AlbumCard />
    <AlbumCard />
    <AlbumCard />
    <AlbumCard />
    <AlbumCard />
    <AlbumCard />
    <AlbumCard />
    <AlbumCard />
  </section>
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
@import "../style/common.scss"


</style>
