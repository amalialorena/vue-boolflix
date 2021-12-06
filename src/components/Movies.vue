<template>
  <section>
    <div class="wrapper">
     <div class="card" v-for="(movie, i) in data" :key="i">
      <Poster :poster="movie.poster_path"/>
      <Title :movieTitle="movie.title" :tvTitle="movie.name"/>
      <OriginalTitle :movieTitle="movie.original_title" :tvTitle="movie.original_name"/>
      <Flag :language="movie.original_language" />
      <Ratings :vote="movie.vote_average"/>    
    </div>
  </div>
  </section>

</template>

<script>
import Flag from "./Flag.vue";
import Title from "./Title.vue";
import OriginalTitle from "./OriginalTitle.vue";
import Poster from "./Poster.vue";
import Ratings from "./Ratings.vue";

export default {
  name: 'Movies',
  components: {
    Flag,
    Poster,
    Title,
    OriginalTitle,
    Ratings
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
    },
   
  },
  methods: {
  
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

  
</style>