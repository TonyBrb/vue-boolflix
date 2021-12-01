/*
Titolo
Titolo Originale
Lingua
Voto
 */

<template>
  <div>
    <ul>
      <li v-for="film in searched_Film"
      :key="film.id">
        <h3>Titolo:</h3> {{film.title}} <h3>Titolo Originale:</h3> {{film.original_title}} <h3>Lingua:</h3> {{film.original_language}} <h3>Voto:</h3> {{film.vote_average}}
      </li>
    </ul>
  </div>
</template>

<script>


export default {
  name: 'Main',
  props:{
    searched_Film: Array
  }
}
</script>

<style lang="scss" scoped>
  div{
    margin-top: -16px;
    background-color: #282C34;
    min-height: calc(100vh - 66px);
    color: white;

    h3{
      margin: 0;
      padding-top: 5px;
      color: red;
    }
  }
</style>