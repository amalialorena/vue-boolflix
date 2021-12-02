<template>
  <div id="app">
    <Search @info="getMovies" />
    <Movies :data="moviesArray"/>
  </div>
</template>

<script>
import Search from "./components/Search.vue";
import Movies from "./components/Movies.vue";
import axios from "axios";

export default {
  name: "App",
  components: {
    Search,
    Movies,
  },

  data() {
    return {
      userMovie: "",
      moviesArray: [],
    };
  },

  computed: {
  
    apiUrl: function () {
      return `https://api.themoviedb.org/3/search/movie?api_key=7008d934756b24d87143ba1e02bcbb09&language=it${this.createQuery(this.userMovie)}`;
    },
  },

  created: function () {},
  
  methods: {
    inputData(input) {
      this.userMovie = input;
      this.getMovies()
    },
    createQuery(item) {
      return "&query=" + item;
    },
    getMovies(query) {
      axios.get(this.apiUrl + query).then((result) => { 
        this.moviesArray = result.data.results;
      });
    },
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
