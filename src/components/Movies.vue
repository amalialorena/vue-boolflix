<template>
  <div class="hello">
    <ul>
      <!-- <li v-for="(movie, i) in moviesArray" :key:"i"> {{movie}}</li> -->
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

  methods: {
    created () {
      this.getMovies();
      console.log(this.moviesArray)
    },
    getMovies () {
      axios.get(this.apiUrl).then((result) =>{
        this.moviesArray = result.data.results.title;
      });
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>