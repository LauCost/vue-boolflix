<template>
  <div id="app">
    <Header @search-film="getTitle" />
    <Main :movies="moviesArray" :shows="showsArray" />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
import axios from "axios";

export default {
  name: "App",
  components: {
    Header,
    Main,
  },

  data() {
    return {
      moviesArray: [],
      showsArray: [],
    };
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
          this.moviesArray = r.data.results;
        });

      axios
        .get(
          "https://api.themoviedb.org/3/search/tv?api_key=58ebf4fc2efccc2902a38beabf175722&language=en-US&page=1&query=" +
            text +
            "&include_adult=false"
        )
        .then((res) => {
          this.showsArray = res.data.results;
        });
    },
  },
};
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
