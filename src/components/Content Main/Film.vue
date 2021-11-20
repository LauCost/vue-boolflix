<template>
  <div class="cont">
    <h1>Films</h1>
    <h2>
      {{ Titolo }}
    </h2>
    <h3>
      {{ NomeOriginale }}
    </h3>
    <img :src="image" alt="" />
    <p v-if="LinguaOriginale == 'en'"><flag iso="gb" /></p>
    <p v-else-if="LinguaOriginale == 'it'"><flag iso="it" /></p>
    <p v-else-if="LinguaOriginale == 'cn'"><flag iso="cn" /></p>
    <p v-else>{{ LinguaOriginale }}</p>
    <p>
      {{ Voto }}
    </p>
    <p>
      <span v-for="(star, i) in getRightVote(Voto)" :key="i">
        <i :class="star"></i>
      </span>
    </p>
  </div>
</template>

<script>
export default {
  props: {
    Titolo: String,
    NomeOriginale: String,
    LinguaOriginale: String,
    Voto: Number,
    image: String,
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
.cont {
  width: 50%;
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: center;
  margin: 20px auto;

  img {
    width: 100%;
  }
}
</style>