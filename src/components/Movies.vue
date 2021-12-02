<template>
  <div class="hello">
     <ul>
      <li v-for="(movie, i) in data" :key="i">{{movie.title}} {{movie.original_title}} {{movie.original_language}} {{movie.vote_average}}</li>
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