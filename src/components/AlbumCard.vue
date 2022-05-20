<template>
  <div class="album m-1">
    <img :src="AlbumItem.poster" :alt="AlbumItem.title" />
    <p class="album__title text-center">{{ AlbumItem.title }}</p>
    <p class="album__author">{{ AlbumItem.author }}</p>
    <p class="album__year">{{ AlbumItem.year }}</p>
  </div>
</template>

<script>
export default {
  name: "AlbumCard",
  props: {
    AlbumItem: Object,
  },
};
</script>

<style lang="scss" scoped>
@import "../style/variables.scss";
@import "../style/common.scss";

.album {
  background-color: $background-color-album;
  min-height: 20rem;

  img {
    width: 100%;
  
  }

  &__title {
    color: $title-text-color;
    text-transform: uppercase;
    font-weight: 550;
  }
}
</style>
