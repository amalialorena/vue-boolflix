<template>
  <section>
    <div class="wrapper">
     <div class="card" v-for="(movie, i) in data" :key="i">
      <Poster :poster="movie.poster_path"/>
      <div class="info-card">
          <Title :movieTitle="movie.title" :tvTitle="movie.name"/>
          <OriginalTitle :movieTitle="movie.original_title" :tvTitle="movie.original_name"/>
          <Ratings :vote="movie.vote_average"/> 
          <Overview :summary="movie.overview"/>   
      </div>
    </div>
  </div>
  </section>

</template>

<script>
import Title from "./Title.vue";
import OriginalTitle from "./OriginalTitle.vue";
import Poster from "./Poster.vue";
import Ratings from "./Ratings.vue";
import Overview from "./Overview.vue";

export default {
  name: 'Movies',
  components: {
    Poster,
    Title,
    OriginalTitle,
    Ratings,
    Overview
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
  .wrapper {
    display: flex;
    flex-wrap: wrap;
  
    .card {
      width: calc(100%/8) ;
      margin: 10px;
      position: relative;
    }

    .info-card {
      display: none;
      position: absolute;
      top: 0;
      right: 0;
      bottom: 6px;
      z-index: 1;
      width:100%;
      background-color: rgba(36, 34, 34, 0.959);
      Overview {
        text-overflow: ellipsis;
        overflow: hidden;
        white-space: nowrap;
        width: 100%;
        height: 100%;
      }
    }
    .card:hover .card {
      background-color: grey;
    }
    .card:hover .info-card {
      display: block;
    }
  }
  
</style>