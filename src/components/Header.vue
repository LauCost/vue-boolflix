<template>
  <Header>
    <div class="search">
      <input
        v-model="searchString"
        type="text"
        placeholder="Search Film and TV Shows"
        @keyup.enter="$emit('search-film', searchString)"
      />
      <!-- <button @click="$emit('search-film', searchString)">Search</button> -->
    </div>
  </Header>
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
header {
  background-color: #2e3a46;
}

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
