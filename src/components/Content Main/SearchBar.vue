<template>
  <div class="search">
    <input v-model="searchString" type="text" placeholder="Search.." />
    <button @click="$emit('search-film', searchString)">Search</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      searchString: "",
    };
  },
};
</script>

<style lang="scss">
.search {
  display: flex;
  justify-content: center;
  input {
    margin: 30px 0;
    width: 50%;
    padding: 20px 0;
    font-size: 25px;
  }

  button {
    margin: 30px 10px;
    padding: 30px;
    border: none;
    background-color: #fff;
    font-size: 25px;
  }
}
</style>