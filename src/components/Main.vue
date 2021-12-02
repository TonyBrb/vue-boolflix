/*
Titolo
Titolo Originale
Lingua
Voto
 */

<template>
  <div>
    <ul>
      <h1 v-if="showFilm==true">Film</h1>
      <li v-for="film in searched_Film"
      :key="film.id">
        <h3>Titolo:</h3> 
        <h5>{{film.title}}</h5>
        <h3>Titolo Originale:</h3>
        <h5>{{film.original_title}} </h5> 
        <div class="lingua" v-if="film.original_language=='en'">
          <h3>Lingua:</h3>
          <img src="../assets/img/en.png" alt="">
          </div>
        <div class="lingua" v-else-if="film.original_language=='it'">
          <h3>Lingua:</h3> 
          <img src="../assets/img/it.png" alt="">
          </div> 
        <div class="lingua" v-else>
          <h3>Lingua:</h3>
          {{film.original_language}}
        </div>
        <h3>Voto:</h3> {{film.vote_average}}
      </li>

      <h1 v-if="showSerie==true">Serie</h1>

      <li v-for="series in searched_Series"
      :key="series.id">
        <h3>Titolo:</h3> 
        <h5>{{series.name}}</h5>
        <h3>Titolo Originale:</h3>
        <h5>{{series.original_name}} </h5> 
        <div class="lingua" v-if="series.original_language=='en'">
          <h3>Lingua:</h3>
          <img src="../assets/img/en.png" alt="">
          </div>
        <div class="lingua" v-else-if="series.original_language=='it'">
          <h3>Lingua:</h3> 
          <img src="../assets/img/it.png" alt="">
          </div> 
        <div class="lingua" v-else>
          <h3>Lingua:</h3>
          {{series.original_language}}
        </div>
        <h3>Voto:</h3> {{series.vote_average}}
      </li>
    </ul>
  </div>
</template>

<script>


export default {
  name: 'Main',
  props:{
    searched_Film: Array,
    searched_Series: Array,
    showFilm: Boolean,
    showSerie: Boolean
  }
}
</script>

<style lang="scss" scoped>
  div{
    font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
    margin-top: -16px;
    background-color: #282C34;
    min-height: calc(100vh - 50px);
    color: white;

    h3{
      margin: 0;
      padding-top: 5px;
      color: red;
    }

    .lingua{
      width: 80px;
      height: 35px;
      img{
        width: 100%;
        margin-top: 10px;
      }
    }
  }
</style>