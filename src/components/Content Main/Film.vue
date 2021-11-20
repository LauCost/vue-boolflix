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
    <p v-if="LinguaOriginale == 'en'"><flag iso="gb" /> | {{ Voto }}</p>
    <p v-else-if="LinguaOriginale == 'it'"><flag iso="it" /> | {{ Voto }}</p>
    <p v-else-if="LinguaOriginale == 'cn'"><flag iso="cn" /> | {{ Voto }}</p>
    <p v-else>{{ LinguaOriginale }} | {{ Voto }}</p>
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