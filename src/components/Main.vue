<template>
  <main>
    <Search @search-film="getTitle" />
    <Movie
      v-for="film in movies"
      :key="film.id"
      :Titolo="film.title"
      :NomeOriginale="film.original_title"
      :LinguaOriginale="film.original_language"
      :Voto="film.vote_average"
    />
    <TvShows
      v-for="show in shows"
      :key="show.id"
      :TitoloTV="show.name"
      :NomeOriginaleTV="show.original_name"
      :LinguaOriginaleTV="show.original_language"
      :VotoTV="show.vote_average"
    />
  </main>
</template>

<script>
import axios from "axios";
import Movie from "./Content Main/Film.vue";
import Search from "./Content Main/SearchBar.vue";
import TvShows from "./Content Main/TvShows.vue";
export default {
  data() {
    return {
      movies: [],
      shows: [],
    };
  },

  components: {
    Movie,
    Search,
    TvShows,
  },

  methods: {
    getTitle(text) {
      console.log(text);
      axios
        .get(
          "https://api.themoviedb.org/3/search/movie?api_key=58ebf4fc2efccc2902a38beabf175722&language=en-US&query=" +
            text +
            "&page=1&include_adult=false"
        )
        .then((r) => {
          this.movies = r.data.results;
        });

      axios
        .get(
          "https://api.themoviedb.org/3/search/tv?api_key=58ebf4fc2efccc2902a38beabf175722&language=en-US&page=1&query=" +
            text +
            "&include_adult=false"
        )
        .then((res) => {
          this.shows = res.data.results;
        });
    },
  },
};
</script>