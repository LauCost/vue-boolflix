<template>
  <div class="cont">
    <h1>Films</h1>
    <h2>
      {{ Titolo }}
    </h2>
    <h3>
      {{ NomeOriginale }}
    </h3>
    <p v-if="LinguaOriginale == 'en'">
      <flag iso="gb" />
    </p>
    <p v-else-if="LinguaOriginale == 'it'">
      <flag iso="it" />
    </p>
    <p v-else-if="LinguaOriginale == 'cn'">
      <flag iso="cn" />
    </p>
    <p v-else>
      {{ LinguaOriginale }}
    </p>
    <p>
      {{ Voto }}
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
  },
};
</script>

<style lang="scss">
.cont {
  width: 50%;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: center;
  margin: 20px auto;
}
</style>