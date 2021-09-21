<template>
  <div class="">
      <div clas = "container">
        <h1 class= "title"> Albums de la página </h1>
         <div class="columns">
             <AlbumCard :album="album" v-for="album in albums" :key="album.id"/>    
         </div>
       </div>
  </div>
</template>
<script>
import axios from 'axios';
import env from '../config/env';
import AlbumCard from '../components/AlbumCard';
export default {
    name :'IndexPage',
    components:{
       AlbumCard:AlbumCard
    },
    data(){
        return{
            albums:[]
        }
    },
    created: async function(){
             console.log('${env.endpoint}/todos');
         /*   axios.get('https://jsonplaceholder.typicode.com/todos').then(response=>{
            this.albums = response.data;*/
            let response = await axios.get('https://jsonplaceholder.typicode.com/todos')
            this.albums = response.data;
        }
        
}
</script>