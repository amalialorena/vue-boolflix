<template>
  <section>
    <div class="wrapper" v-if="data">
     <ul v-for="(movie, i) in data" :key="i">
      <li >{{movie.title}}</li>
      <li>{{movie.original_title}}</li>
      <li v-if="movie.original_language ==='it'">
          <div class="flag"><img src="../assets/img/italy.png" alt=""></div>
      </li>
      <li v-else-if="movie.original_language ==='en'">
        <div class="flag"><img src="../assets/img/united-states-of-america.png" alt=""></div>
      </li>
      <li v-else-if="movie.original_language ==='de'">
        <div class="flag"><img src="../assets/img/germany.png" alt=""></div>
      </li>
      <li v-else class="flag">
        <div class="flag"><img src="../assets/img/rainbow-flag.png" alt=""></div>
      </li>
      <li>{{movie.vote_average}}</li>
    </ul>
  </div>
  <div v-else>
    <h3>search a movie</h3>
  </div>
  
  </section>
  
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
  section {
   .flag {
     width: 50px;
     height: 40px;
     img {
       height: 100%;
     }
   }

  }

</style>