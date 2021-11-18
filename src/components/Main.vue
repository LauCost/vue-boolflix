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
  </main>
</template>

<script>
import axios from "axios";
import Movie from "./Content Main/Film.vue";
import Search from "./Content Main/SearchBar.vue";
export default {
  data() {
    return {
      movies: [],
    };
  },

  components: {
    Movie,
    Search,
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
    },
  },
};
</script>