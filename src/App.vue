<template>
  <div>
    <Header @textToSearch="filmToSearch"/>
    <Main :searched_Film="array_film"/>
  </div>
</template>

<script>

import axios from "axios";

import Header from "./components/Header.vue"
import Main from "./components/Main.vue"

export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data(){
    return{
      apiURL:'https://api.themoviedb.org/3/search/movie?api_key=927cd3cd4af5831d64e0b7aa05687c5b&language=it-IT&query',
      film_name:'',
      array_film:[]
    }
  },
  methods:{
    filmToSearch(text){
      this.film_name = text;
      console.log(this.film_name);
      this.getApi();
    },
    getApi(){
      axios.get(`${this.apiURL}=${this.film_name}`)
      .then( r =>{
        //console.log(r.data.results);
        this.array_film = r.data.results;
        console.log(this.array_film);
      })
      .catch( e =>{
        console.log(e);
      })
    }
  },
  mounted(){
    // this.getApi();
  }
}
</script>

<style lang="scss">

</style>
