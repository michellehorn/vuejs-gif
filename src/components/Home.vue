<template>
  <div>
    <div class="search-box">
      <h1 class="f-tillium">Procure seu gif aqui!</h1>
      <div class="form-inline text-center">
        <input v-model="searchBox" type="text" placeholder="Digite o que está procurando">
        <div class="form-inline">
          <button class="btn btn-primary" @click="getByInput()">
            Efetuar busca
            <i class="fas fa-search"></i>
          </button>
        </div>
      </div>
      <div class="p-1">
        <span>Número de resultados:</span>
        <select v-model="numberOfResults" name id>
          <option value="5">5</option>
          <option value="10">10</option>
          <option value="15">15</option>
        </select>
      </div>
    </div>
    <div v-for="(gif, index) in this.info" :key="index" class="body-home">
      <div class="box-gif">
        <img :src="gif.images.fixed_height.url" alt>
      </div>
    </div>
  </div>
</template>

<script>
const axios = require("axios");

export default {
  name: "Home",
  props: {
    searchBox: { type: String, default: "gifs" },
    numberOfResults: { type: String, default: "5" }
  },
  data: () => ({
    info: null
  }),
  mounted() {
    this.getByInput();
  },

  methods: {
    getByInput() {
      this.transformString();
      axios
        .get(
          `http://api.giphy.com/v1/gifs/search?q=${
            this.searchBox
          }&api_key=1XBSXCdDRqdJagR2YYUOcF6pmNeXSJKx&limit=${
            this.numberOfResults
          }`
        )
        .then(response => (this.info = response.data.data));
    },
    transformString() {
      this.searchBox = this.searchBox.replace(" ", "+");
    }
  }
};
</script>

<style lang="scss">
.body-home {
  display: inline-flex;
  max-width: 100%;
  .box-gif {
    width: 35%;
    img {
      padding: 1em 2em;
      border-radius: 8%;
      max-height: 100px;
      &:hover {
        box-shadow: 2px 2px 8px gray;
        cursor: pointer;
        padding: 0em 0em;
        max-height: 120px;
      }
    }
  }
}
.search-box {
  input {
    font-size: 18px;
    padding: 8px;
    width: 250px;
    height: 30px;
    text-align: center;
    border: none;
    border-radius: 8px;
  }
  margin-bottom: 50px;
}
</style>
