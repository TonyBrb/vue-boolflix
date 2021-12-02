<template>
  <div>
    <Header @textToSearch="filmToSearch"/>
    <Main :searched_Film="array_film" :searched_Series="array_series" :showFilm="showFilm" :showSerie="showSerie"/>
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
      apiURLFilm:'https://api.themoviedb.org/3/search/movie?api_key=927cd3cd4af5831d64e0b7aa05687c5b&language=it-IT&query',
      apiURLSeries: 'https://api.themoviedb.org/3/search/tv?api_key=927cd3cd4af5831d64e0b7aa05687c5b&language=it-IT&query',
      film_name:'',
      array_film:[],
      array_series: [],
      showFilm: false,
      showSerie: false
    }
  },
  methods:{
    filmToSearch(text){
      this.film_name = text;
      console.log(this.film_name);
      this.getApi();
    },
    getApi(){
      axios.get(`${this.apiURLFilm}=${this.film_name}`)
      .then(r =>{
        this.array_film = r.data.results;
        if(this.array_film.length > 0) this.showFilm=true;
        console.log(this.array_film);
      })
      .catch( e =>{
        console.log(e);
      });
      axios.get(`${this.apiURLSeries}=${this.film_name}`)
      .then(r =>{
        this.array_series = r.data.results;
        if(this.array_series.length > 0) this.showSerie=true;
        console.log(this.array_series);
      })
      .catch( e =>{
        console.log(e);
      });

    }
  },
  mounted(){
    // this.getApi();
  }
}
</script>

<style lang="scss">

</style>
