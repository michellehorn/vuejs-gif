<template>
  <div class="nav-bar">
    <ul class="nav">
     <router-link class="nav-item" to="/home">Home</router-link>
      <router-link class="nav-item" to="/list">Favoritos</router-link>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Tab'
}
</script>

<style lang="scss">
.nav-bar {
  background-color: rgb(41, 34, 34);
  margin: 0;
  top: 0;
  left: 0;
  height: 65px;
  position: fixed;
  width: 100%;
  box-shadow: 0px 3px 4px gray;

  .nav {
    list-style: none !important;
    display: flex;
    .nav-item {
      color: white;
      font-family: 'Open Sans', sans-serif;
      padding: 0.5em 3em;
      text-decoration: none;
      &:hover {
        cursor: pointer;
        color: lightgray;
      }
    }
  }
}
</style>
