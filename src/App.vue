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
    Movies
  },
  data() {
    return {
      userMovie: "",
      moviesArray: [],
      movieUrl:`https://api.themoviedb.org/3/search/movie?api_key=7008d934756b24d87143ba1e02bcbb09&language=it&query=`,
      seriesUrl:`https://api.themoviedb.org/3/search/tv?api_key=7008d934756b24d87143ba1e02bcbb09&language=it&query=`
    };
  },
 
  methods: {
    getMovies(query) {
      this.userMovie = query;
      axios.get(this.movieUrl+this.userMovie).then((result) => { 
        this.moviesArray = result.data.results;
      });
      axios.get(this.seriesUrl+this.userMovie).then((result) => { 
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
}
* {
   margin: 0;
   padding: 0;
   box-sizing:border-box;
}
body {
  background-color: #101010
}
</style>
