<template>
  <main>
    <Movie
      v-for="film in movies"
      :key="film.id"
      :Titolo="film.title"
      :NomeOriginale="film.original_title"
      :LinguaOriginale="film.original_language"
      :Voto="film.vote_average"
      :image="'https://image.tmdb.org/t/p/w500/' + film.poster_path"
    />
    <TvShows
      v-for="show in shows"
      :key="show.id"
      :TitoloTV="show.name"
      :NomeOriginaleTV="show.original_name"
      :LinguaOriginaleTV="show.original_language"
      :VotoTV="show.vote_average"
      :imageTV="'https://image.tmdb.org/t/p/w500/' + show.poster_path"
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