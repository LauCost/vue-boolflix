<template>
  <Header>
    <div class="search">
      <input type="text" placeholder="Search.." />
      <button>Search</button>
    </div>
  </Header>
</template>




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
