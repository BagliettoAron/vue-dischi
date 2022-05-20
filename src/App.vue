<template>
  <div id="app">
  <AlbumList />
    
  </div>
</template>

<script>
import AlbumList from "./components/AlbumList.vue";



export default {
  name: 'App',
  components: {
    AlbumList,
    
}
}
</script>

<style lang="scss">
@import "./style/common.scss";

#app {

}
</style>
