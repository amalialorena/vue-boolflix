<template>
  <div id="app">
    <Search @info="getMovies" />
    <h2>Popular movies</h2>
    <Movies :data="moviesArray" />
    <Movies :trending="trendingMovies"/>
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
      trendingMovies: [],
      movieUrl:`https://api.themoviedb.org/3/search/movie?api_key=7008d934756b24d87143ba1e02bcbb09&language=it&query=`,
      seriesUrl:`https://api.themoviedb.org/3/search/tv?api_key=7008d934756b24d87143ba1e02bcbb09&language=it&query=`,
      popularUrl: `https://api.themoviedb.org/3/movie/popular?api_key=7008d934756b24d87143ba1e02bcbb09&language=en-US&page=1`,
      trendingUrl:'https://api.themoviedb.org/3/trending/all/day?api_key=7008d934756b24d87143ba1e02bcbb09'
    };
  },
  created () {
    this.getPopular();
    this.getTrending()
  },
  methods: {
    getPopular() {
      axios.get(this.popularUrl).then((result) => { 
        this.moviesArray = result.data.results;
      });
    },
    getTrending() {
      axios.get(this.trendingUrl).then((result) => {
        this.trendingMovies = result.data.results
      });
    },
    getMovies(query) {
      this.userMovie = query;
      axios.get(this.popularUrl+this.userMovie).then((result) => { 
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
  h2 {
    color: white;
  } 
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
