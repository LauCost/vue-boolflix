<template>
  <div class="cont">
    <h1>TV Shows</h1>
    <h2>
      {{ TitoloTV }}
    </h2>
    <h3>
      {{ NomeOriginaleTV }}
    </h3>
    <p v-if="LinguaOriginaleTV == 'en'">
      <flag iso="gb" />
    </p>
    <p v-else-if="LinguaOriginaleTV == 'it'">
      <flag iso="it" />
    </p>
    <p v-else-if="LinguaOriginaleTV == 'cn'">
      <flag iso="cn" />
    </p>
    <p v-else>
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
</style>