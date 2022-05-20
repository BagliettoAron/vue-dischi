<template>
<div class="album">
    <img :src="AlbumItem.poster" alt="AlbumItem.title">
    <p class="title" >{{AlbumItem.title}}</p>
    <p class="author">{{AlbumItem.author}}</p>
    <p class="year" >{{AlbumItem.year}}</p>


</div>
  
</template>


<script>

export default {
    name: "AlbumCard",
    props: {
       AlbumItem: Object 
    }

}

</script>


<style lang="scss" scoped>

@import "../style/variables.scss";

.album{

    img {
        width: 100%;

    }
}

</style>