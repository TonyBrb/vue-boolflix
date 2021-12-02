/*
Titolo
Titolo Originale
Lingua
Voto
 */

<template>
  <main>
    <ul>
      <h1 v-if="showFilm==true">Film</h1>
      <li v-for="film in searched_Film"
      :key="film.id">
        <div class="cover">
          <img :src='`https://image.tmdb.org/t/p/w342/${film.backdrop_path}`'  alt=''>
        </div>
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
        <h3>Voto:</h3> 
        <h5>{{film.vote_average/2}}
        </h5>
        <div class="star" v-if="(film.vote_average/2) == 0">
          <i class="far fa-star"></i>
          <i class="far fa-star"></i>
          <i class="far fa-star"></i>
          <i class="far fa-star"></i>
          <i class="far fa-star"></i>
        </div>
        <div class="star" v-if="(film.vote_average/2) >= 1 && (film.vote_average/2) < 2">
          <i class="fas fa-star"></i>
          <i class="far fa-star"></i>
          <i class="far fa-star"></i>
          <i class="far fa-star"></i>
          <i class="far fa-star"></i>
        </div>
        <div class="star" v-if="(film.vote_average/2) >= 2 && (film.vote_average/2) < 3">
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="far fa-star"></i>
          <i class="far fa-star"></i>
          <i class="far fa-star"></i>
        </div>
        <div class="star" v-if="(film.vote_average/2) >= 3 && (film.vote_average/2) < 4">
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="far fa-star"></i>
          <i class="far fa-star"></i>
        </div>
        <div class="star" v-if="(film.vote_average/2) >= 4 && (film.vote_average/2) < 5">
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="far fa-star"></i>
        </div>
        <div class="star" v-if="(film.vote_average/2) == 5">
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
        </div>
      </li>

      <h1 v-if="showSerie==true">Serie</h1>

      <li v-for="series in searched_Series"
      :key="series.id">
        <div class="cover">
          <img :src='`https://image.tmdb.org/t/p/w342/${series.backdrop_path}`' alt=''>
        </div>
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
        <h3>Voto:</h3> 
        <h5>{{series.vote_average/2}}</h5> 
         <div class="star" v-if="(series.vote_average/2) == 0">
          <i class="far fa-star"></i>
          <i class="far fa-star"></i>
          <i class="far fa-star"></i>
          <i class="far fa-star"></i>
          <i class="far fa-star"></i>
        </div>
        <div class="star" v-if="(series.vote_average/2) >= 1 && (series.vote_average/2) < 2">
          <i class="fas fa-star"></i>
          <i class="far fa-star"></i>
          <i class="far fa-star"></i>
          <i class="far fa-star"></i>
          <i class="far fa-star"></i>
        </div>
        <div class="star" v-if="(series.vote_average/2) >= 2 && (series.vote_average/2) < 3">
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="far fa-star"></i>
          <i class="far fa-star"></i>
          <i class="far fa-star"></i>
        </div>
        <div class="star" v-if="(series.vote_average/2) >= 3 && (series.vote_average/2) < 4">
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="far fa-star"></i>
          <i class="far fa-star"></i>
        </div>
        <div class="star" v-if="(series.vote_average/2) >= 4 && (series.vote_average/2) < 5">
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="far fa-star"></i>
        </div>
        <div class="star" v-if="(series.vote_average/2) == 5">
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
        </div>
      </li>
    </ul>
  </main>
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
  main{
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

    h5{
      margin-top: 0;
    }


    li{
      width: 342px;
      border: 1px solid white;
      margin-bottom: 100px;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      .star{
        margin-bottom: 20px;
      }
    }

    .lingua{
      width: 80px;
      img{
        width: 100%;
        margin-top: 10px;
      }
    }
  }
</style>