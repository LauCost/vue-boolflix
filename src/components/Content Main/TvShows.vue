<template>
  <div class="cont">
    <img :src="imageTV" alt="" />
    <div class="hover">
      <h2>TV Shows</h2>
      <p>Title: {{ TitoloTV }}</p>
      <p>Original title: {{ NomeOriginaleTV }}</p>
      <p>
        Vote:

        <span v-for="(star, i) in getRightVote(VotoTV)" :key="i">
          <i :class="star"></i>
        </span>
      </p>
      <p v-if="LinguaOriginaleTV == 'en'">
        Original language: <flag iso="gb" />
      </p>
      <p v-else-if="LinguaOriginaleTV == 'it'">
        Original language: <flag iso="it" />
      </p>
      <p v-else-if="LinguaOriginaleTV == 'cn'">
        Original language: <flag iso="cn" />
      </p>
      <p v-else>Original language: {{ LinguaOriginaleTV }}</p>
      <p>Overview: {{ lessOverview(tramaTV) }}</p>
    </div>
  </div>
</template>


<script>
export default {
  props: {
    TitoloTV: String,
    NomeOriginaleTV: String,
    LinguaOriginaleTV: String,
    VotoTV: Number,
    imageTV: String,
    tramaTV: String,
  },

  methods: {
    getRightVote(number) {
      let int = Math.ceil(number / 2);
      const starFull = "fas fa-star";
      const starEmpty = "far fa-star";
      const listStar = [];
      while (listStar.length < 5) {
        if (int > 0) {
          listStar.push(starFull);
          int--;
        } else {
          listStar.push(starEmpty);
        }
      }
      return listStar;
    },

    lessOverview(tramaTV) {
      if (tramaTV.length > 200) {
        return tramaTV.slice(0, 200) + "...";
      }
      return tramaTV;
    },
  },
};
</script>


<style lang="scss">
</style>