<template>
  <section>
    <div class="wrapper">
     <ul v-for="(movie, i) in data" :key="i">
      <li><img :src="`https://image.tmdb.org/t/p/w342/${movie.poster_path}`" alt="movie poster"></li>
      <li >{{movie.title}}{{movie.name}}</li>
      <li>{{movie.original_title}}{{movie.original_name}}</li>
      <li><Flag :language="movie.original_language" /></li>
      <li>original vote {{movie.vote_average}}</li>
      <li class="stars">
          <div class="star" v-for="(star, i) in stars(movie.vote_average)" :key="i"></div>
      </li>     
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
    },
   
  },
  methods: {
     stars: function(vote) {
      let stars = [];
      let star = "";
      let divideVote = vote / 2 ;
      let roundNum = (Math.round(divideVote));
      for(let i = 0; i < roundNum; i ++) {
        stars.push(star)
      }
      return stars
    }
  }
  
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.stars {
  display: flex;
  .star {
    height: 20px;
    width: 20px;
    background-color: red;
    border: 1px solid black;
  }

}
  
</style>