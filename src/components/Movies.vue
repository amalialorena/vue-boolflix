<template>
  <div class="hello">
    <ul>
      <li v-for="(movie, i) in moviesArray" :key="i" >{{movie.title}} {{movie.original_title}} {{movie.original_language}} {{movie.vote_average}}</li>
      <!-- <li>{{moviesArray}}</li> -->
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
      return {
          apiUrl: "https://api.themoviedb.org/3/search/movie?api_key=7008d934756b24d87143ba1e02bcbb09&query=harry+potter",
          moviesArray: [],
      };
  },

   created: function () {
      this.getMovies();
      console.log(this.moviesArray)
    },
  methods: {

    getMovies () {
      axios.get(this.apiUrl).then((result) => {
        this.moviesArray = result.data.results;
      });
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>