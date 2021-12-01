<template>
  <div class="hello">
    <input type="text" v-model="userMovie">
    <button @click.prevent="getMovies">Search</button>
    <ul>
      <li v-for="(movie, i) in moviesArray" :key="i" >{{movie.title}} {{movie.original_title}} {{movie.original_language}} {{movie.vote_average}}</li>
    </ul>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: 'Movies',
  props: {
   
  },

  data () {
    const movieSearch = "harry+potter";
      return {
          userMovie: "",
          movieSearch,
          moviesArray: [],
      };
  },
  computed: {
    query: function() {
      return "&query=" + this.userMovie;
    },
      apiUrl: function () {
        return `https://api.themoviedb.org/3/search/movie?api_key=7008d934756b24d87143ba1e02bcbb09${this.userMovie ? this.query: ''}`;
      }
  },
  created: function () {
    // this.getMovies();
  },
  methods: {
    getMovies () {
      axios.get(this.apiUrl).then((result) => {
        this.moviesArray = result.data.results ;
      });
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>