<template>

  <div class="">
  
    <select name="" id=""  @change="$emit('scelta', genere)" v-model="genere">
        <option value=""></option>
        <option value="rock" >Rock</option>
        <option value="pop">Pop</option>
        <option value="jazz">Jazz</option>
        <option value="metal">Metal</option>
    </select>
  
  </div>

</template>


<script>

export default {
    name: 'SearchElement',
    data: function () {
        return {
            genere: ''
        }
    }
    


}

</script>

<style lang="scss" coped>

</style>