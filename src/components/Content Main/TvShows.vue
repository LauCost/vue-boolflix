<template>
  <div class="cont">
    <h1>TV Shows</h1>
    <h2>
      {{ TitoloTV }}
    </h2>
    <h3>
      {{ NomeOriginaleTV }}
    </h3>
    <p>
      {{ LinguaOriginaleTV }}
    </p>
    <p>
      {{ VotoTV }}
    </p>
  </div>
</template>


<script>
export default {
  props: {
    TitoloTV: String,
    NomeOriginaleTV: String,
    LinguaOriginaleTV: String,
    VotoTV: Number,
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