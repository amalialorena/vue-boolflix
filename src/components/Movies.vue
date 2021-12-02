<template>
  <div class="hello">
     <ul v-for="(movie, i) in data" :key="i">
      <li >{{movie.title}}</li>
      <li>{{movie.original_title}}</li>
      <li v-if="movie.original_language ==='it'">italian</li>
      <li v-else-if="movie.original_language ==='en'">english</li>
      <li v-else>other</li>
      <li>{{movie.vote_average}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Movies',
  props: {
   data: Array,
  },

  data () {
    const movieSearch = "harry+potter";
      return {
          movieSearch,
      };
  },

};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>