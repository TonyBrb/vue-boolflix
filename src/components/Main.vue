/*
Titolo
Titolo Originale
Lingua
Voto
 */

<template>
  <main>
    <h1 v-if="showFilm==true">Film</h1>
    <div class="container">
    
    <ul v-for="film in searched_Film"
              :key="film.id">
      <div class="flip-card">
        <div class="flip-card-inner">
          <div class="flip-card-front">
             <li >
                <div class="cover">
                  <img :src='`https://image.tmdb.org/t/p/w342/${film.backdrop_path}`' :title="film.title" :alt='film.title'>
                </div>
            </li>
          </div>
          <div class="flip-card-back">
             <li>
                  <span><strong>Titolo:</strong> {{film.title}}</span> <br>
                  <span><strong>Titolo originale:</strong> {{film.original_title}}</span> <br>
                  <span><strong>Lingua:</strong></span>
                  <div class="lingua" v-if="film.original_language=='en'">
                    <img src="../assets/img/en.png" alt="">
                    </div> 
                  <div class="lingua" v-else-if="film.original_language=='it'">
                    <span><strong>Lingua:</strong></span> 
                    <img src="../assets/img/it.png" alt="">
                    </div> 
                  <div class="lingua" v-else>
                    <span><strong>Lingua:</strong> {{film.original_language}}</span>
                  </div><br>
                  <span><strong>Voto:</strong> {{Math.round(film.vote_average/2)}}</span>
                  <div class="star">
                    <i 
                    v-for="(item,index) in 5"
                    :key="index"
                    :class="index < Math.round(film.vote_average/2) ? 'fas' : 'far'"
                    class="fa-star"></i>
                  </div>
                  <span><strong>Overview:</strong> {{film.overview}}</span>
             </li>
          </div>
        </div>
      </div>
      </ul>
      </div>
      <h1 v-if="showSerie==true">Serie TV</h1>
      <div class="container">
       <ul v-for="series in searched_Series"
          :key="series.id">
            <div class="flip-card">
              <div class="flip-card-inner">
                <div class="flip-card-front">
                  <li >
                      <div class="cover">
                        <img :src='`https://image.tmdb.org/t/p/w342/${series.backdrop_path}`' :title="series.name" :alt='series.name'>
                      </div>
                  </li>
                </div>
              <div class="flip-card-back">
                <li>
                  <span><strong>Titolo:</strong> {{series.name}}</span> <br>
                  <span><strong>Titolo originale:</strong> {{series.original_name}}</span> <br>
                  <span><strong>Lingua:</strong></span>
                  <div class="lingua" v-if="series.original_language=='en'">
                    <img src="../assets/img/en.png" alt="">
                    </div> 
                  <div class="lingua" v-else-if="series.original_language=='it'">
                    <h3>Lingua:</h3> 
                    <img src="../assets/img/it.png" alt="">
                    </div> 
                  <div class="lingua" v-else>
                    <span><strong>Lingua:</strong> {{series.original_language}}</span>
                  </div><br>
                  <span><strong>Voto:</strong> {{Math.round(series.vote_average/2)}}</span>
                  <div class="star">
                    <i 
                    v-for="(item,index) in 5"
                    :key="index"
                    :class="index < Math.round(series.vote_average/2) ? 'fas' : 'far'"
                    class="fa-star"></i>
                  </div>
                  <span><strong>Overview:</strong> {{series.overview}}</span>
                </li>
                </div>
              </div>
            </div>
      </ul>
      </div>
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
    background-color: #282C34;
    min-height: calc(100vh - 50px);
    color: white;

    .container{
      width: 90%;
      display: flex;
      flex-wrap: wrap;
      margin: 0 auto;
    }

    h1{
      margin-left: 8%;
    }

    h3{
      margin: 0;
      padding-top: 5px;
      color: red;
    }

    h5{
      margin-top: 0;
    }

    ul{
      list-style: none;
    }

    li{
      width: 342px;
      height: 300px;
      border-top-radius: 20px;
      text-align: initial;
      overflow: auto;
      .star{
        margin-bottom: 20px;
      }

      span{
        strong{
          color: red;
        }
      }
    }

    .lingua{
      display: inline-block;
      width: 15px;
      img{
        width: 100%;
        margin-top: 10px;
      }
    }

    .cover{
      img{
        border-radius: 20px;
      }
    }


    .flip-card {
  background-color: transparent;
  width: 342px;
  min-height: 300px;
  perspective: 1000px;
}

.flip-card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  text-align: center;
  transition: transform 0.6s;
  transform-style: preserve-3d;
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
}

.flip-card:hover .flip-card-inner {
  transform: rotateY(180deg);
  cursor: pointer;
}

.flip-card-front, .flip-card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
}

.flip-card-front {
  background-color: #bbb;
  color: black;
}

.flip-card-back {
  background-color: #2980b9;
  color: white;
  transform: rotateY(180deg);
}
  }
</style>