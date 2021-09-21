<template lang="html">
    <div class="box column is-one-quarter">
      <h3>{{album.title}}</h3>
      <a href="#"class="button is-primary"> Ver álbum</a>
      <Nuxt-link :to="`/albums/${album.id}`" class="button is-primary">ir al album </Nuxt-link>
      
   </div>   
</template>

<script>
export default {
    name:'AlbumCard',
    props:{
        album: Object
    }
}
</script>
<style lang="css">
.box{
    padding: 1em;
}
h3{
    min-height:4em;
} 
</style>