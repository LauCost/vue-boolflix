<template>
  <div class="cont">
    <img :src="image" alt="" />
    <div class="hover">
      <h2>Films</h2>
      <p>Title: {{ Titolo }}</p>
      <p>Original title: {{ NomeOriginale }}</p>
      <p>
        Vote:

        <span v-for="(star, i) in getRightVote(Voto)" :key="i">
          <i :class="star"></i>
        </span>
      </p>
      <p v-if="LinguaOriginale == 'en'">Original language: <flag iso="gb" /></p>
      <p v-else-if="LinguaOriginale == 'it'">
        Original language: <flag iso="it" />
      </p>
      <p v-else-if="LinguaOriginale == 'cn'">
        Original language: <flag iso="cn" />
      </p>
      <p v-else>Original language: {{ LinguaOriginale }}</p>
      <p>Overview: {{ lessOverview(trama) }}</p>
    </div>
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
    trama: String,
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

    lessOverview(trama) {
      if (trama.length > 350) {
        return trama.slice(0, 350) + "...";
      }
      return trama;
    },
  },
};
</script>

<style lang="scss">
.cont {
  width: 13%;
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  justify-content: space-between;
  margin: 15px;
  background-color: #000000;
  height: 450px;

  img {
    width: 100%;
    height: 100%;
  }

  .hover {
    display: none;
    padding: 20px 0;
  }

  p,
  h2 {
    margin: 5px 10px;
    color: #fff;
  }
}

.cont:hover img {
  display: none;
}

.cont:hover .hover {
  display: block;
}
</style>