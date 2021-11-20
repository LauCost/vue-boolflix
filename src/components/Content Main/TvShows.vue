<template>
  <div class="cont">
    <h1>TV Shows</h1>
    <h2>
      {{ TitoloTV }}
    </h2>
    <h3>
      {{ NomeOriginaleTV }}
    </h3>
    <img :src="imageTV" alt="" />
    <p v-if="LinguaOriginaleTV == 'en'"><flag iso="gb" /> | {{ VotoTV }}</p>
    <p v-else-if="LinguaOriginaleTV == 'it'">
      <flag iso="it" /> | {{ VotoTV }}
    </p>
    <p v-else-if="LinguaOriginaleTV == 'cn'">
      <flag iso="cn" /> | {{ VotoTV }}
    </p>
    <p v-else>{{ LinguaOriginaleTV }} | {{ VotoTV }}</p>
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
};
</script>


<style lang="scss">
</style>