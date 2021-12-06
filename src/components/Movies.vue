<template>
  <section>
    <div class="wrapper">
     <ul v-for="(movie, i) in data" :key="i">
      <Poster :poster="movie.poster_path"/>
      <Title :movieTitle="movie.title" :tvTitle="movie.name"/>
      <OriginalTitle :movieTitle="movie.original_title" :tvTitle="movie.original_name"/>
      <Flag :language="movie.original_language" />
      <li>original vote {{movie.vote_average}}</li>
      <li class="stars">
          <div class="star filled-star" v-for="i in generateStars(movie.vote_average)" :key="i"><i class="fas fa-star"></i></div>
          <div class="star hollow-star" v-for="j in generateHollowStars()" :key="j"><i class="fas fa-star"></i></div>
      </li>     
    </ul>
  </div>
  </section>

</template>

<script>
import Flag from "./Flag.vue";
import Title from "./Title.vue";
import OriginalTitle from "./OriginalTitle.vue";
import Poster from "./Poster.vue";

export default {
  name: 'Movies',
  components: {
    Flag,
    Poster,
    Title,
    OriginalTitle,
  },
  props: {
   data: Array,
  },
  data: function () {
    return {
      language: 'it',
      roundNum: null,
    }
  },
  computed: {
    movieLanguage: function() {
      return this.language;
    },
   
  },
  methods: {
     generateStars: function(vote) {
      let divideVote = vote / 2 ;
      this.roundNum = (Math.round(divideVote));
      return this.roundNum
    },
    generateHollowStars: function() {
      let hollowStars = 5 - this.roundNum;
      console.log(hollowStars);
      return hollowStars
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.stars {
  display: flex;
  .star {
    i {
      text-shadow: 0 0 1px #745f03;
    }  
  }
  .filled-star i {
       color:rgb(255, 208, 0);
     }
  .hollow-star i {
       color: rgb(201, 199, 199);
     }
}
  
</style>