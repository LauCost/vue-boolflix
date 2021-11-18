<template>
  <Header>
    <Search />
  </Header>
</template>

<script>
import Search from "./Content Header/SearchBar.vue";
export default {
  components: {
    Search,
  },
};
</script>


<style lang="scss">
header {
  background-color: #2e3a46;
}
</style>
