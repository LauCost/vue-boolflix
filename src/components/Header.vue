<template>
  <Header>
    <div class="search">
      <h1>BOOLFLIX</h1>
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
  background-color: #000000;
}

.search {
  display: flex;
  justify-content: space-around;
  align-items: center;

  h1 {
    color: #a00000;
  }
  input {
    margin: 30px 0;
    width: 20%;
    padding: 20px 0 20px 10px;
    font-size: 25px;
  }

  /* button {
    margin: 30px 10px;
    padding: 30px;
    border: none;
    background-color: #fff;
    font-size: 25px;
  } */
}
</style>
