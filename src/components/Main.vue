<template>
  <div>
    <ul>
      <li></li>
    </ul>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      movies: [],
    };
  },

  mounted() {
    axios
      .get(
        "https://api.themoviedb.org/3/search/movie?api_key=58ebf4fc2efccc2902a38beabf175722&language=en-US&query=&page=1&include_adult=false"
      )
      .then((r) => {
        this.movies = r.data;
      });
  },
};
</script>