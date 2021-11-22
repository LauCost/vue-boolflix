<template>
  <div class="cont">
    <img :src="imageTV" alt="" />
    <div class="hover">
      <h2>TV Shows</h2>
      <p>
        {{ TitoloTV }}
      </p>
      <p>
        {{ NomeOriginaleTV }}
      </p>
      <p v-if="LinguaOriginaleTV == 'en'"><flag iso="gb" /></p>
      <p v-else-if="LinguaOriginaleTV == 'it'">
        <flag iso="it" />
      </p>
      <p v-else-if="LinguaOriginaleTV == 'cn'">
        <flag iso="cn" />
      </p>
      <p v-else>{{ LinguaOriginaleTV }}</p>
      <p>
        <span v-for="(star, i) in getRightVote(Voto)" :key="i">
          <i :class="star"></i>
        </span>
      </p>
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
  },
};
</script>


<style lang="scss">
</style>