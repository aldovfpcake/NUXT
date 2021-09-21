<template lang="html">
    <div class="container">
        <header>
         <nuxt-link to="/"> Regresar</nuxt-link> 
        </header>
        <h1 class="title">{{album.title}} </h1>
        <div class="columns is-multiline ">
            <div class="column is-one-quarter" >
            
              <img :src="album.url" :alt="album.title" />  
              <img :scr="album.url" :alt="album.title" />
            </div>
         </div>    
    </div>
</template>
<script>
import router from 'vue-router';
import axios from 'axios';
export default {
    name: 'AlbunIndvPage',
    data(){
        return{
        album: {},
        photos:[]
        }
    },
    
    created: async function() {
      let albumid = this.$route.params.id;
      let miuri = `https://jsonplaceholder.typicode.com/photos/${albumid}`;
      console.log(miuri);
      console.log(albumid);
     /* const newLocal=`https://jsonplaceholder.typicode.com/photos/${this.$route.params.id}`*/
           /*axios.get('${miuri}')*/
          /* axios.get(`https://jsonplaceholder.typicode.com/photos/${albumid}`)
           .then(albumResponse=>{
                this.album =albumResponse.data;
            })  */
            
       let albumResponse = await axios.get(`https://jsonplaceholder.typicode.com/photos/${albumid}`);
       this.album = albumResponse.data;

         console.log(this.album);
    }   
}
</script>
<style scoped>
 .container{
     text-align: center;
 }
 .title{
     margin-top: 100px;
 }
</style>