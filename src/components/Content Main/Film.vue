<template>
  <div class="cont">
    <h2>
      {{ Titolo }}
    </h2>
    <h3>
      {{ NomeOriginale }}
    </h3>
    <p>
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
  justify-content: space-around;
  margin: 20px auto;
}
</style>