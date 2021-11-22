<template>
  <main>
    <Movie
      v-for="film in movies"
      :key="film.id"
      :image="'https://image.tmdb.org/t/p/w500' + film.poster_path"
      :Titolo="film.title"
      :NomeOriginale="film.original_title"
      :LinguaOriginale="film.original_language"
      :Voto="film.vote_average"
      :trama="film.overview"
    />
    <TvShows
      v-for="show in shows"
      :key="show.id"
      :imageTV="'https://image.tmdb.org/t/p/w500' + show.poster_path"
      :TitoloTV="show.name"
      :NomeOriginaleTV="show.original_name"
      :LinguaOriginaleTV="show.original_language"
      :VotoTV="show.vote_average"
    />
  </main>
</template>

<script>
import Movie from "./Content Main/Film.vue";
import TvShows from "./Content Main/TvShows.vue";
export default {
  props: {
    movies: Array,
    shows: Array,
  },

  components: {
    Movie,
    TvShows,
  },
};
</script>


<style lang="scss">
main {
  background-color: #434343;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  min-height: 84.6vh;
}
</style>