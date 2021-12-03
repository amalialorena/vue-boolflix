<template>
  <section>
    <div class="wrapper">
     <ul v-for="(movie, i) in data" :key="i">
      <li><img :src="`https://image.tmdb.org/t/p/w342/${movie.poster_path}`" alt="movie poster"></li>
      <li >{{movie.title}}{{movie.name}}</li>
      <li>{{movie.original_title}}{{movie.original_name}}</li>
      <li><Flag :language="movie.original_language" /></li>
      <li>{{movie.vote_average}}</li>     
    </ul>
  </div>
  </section>

</template>

<script>
import Flag from "./Flag.vue";

export default {
  name: 'Movies',
  components: {
    Flag,
  },
  props: {
   data: Array,
  },
  data: function () {
    return {
      language: 'it',
    }
  },
  computed: {
    movieLanguage: function() {
      return this.language;
    }
 
  }
  
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>