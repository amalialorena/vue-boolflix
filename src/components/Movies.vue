<template>
  <section>
    <div class="wrapper">
       <Card 
        v-for="(film, i) in data" :key="i"
         :movie="film" 
      /> 
    </div>
  </section>
</template>

<script>
import Card from "./Card.vue";


export default {
  name: "Movies",
  components: {
   Card,
  },
  props: {
    data: Array,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  .wrapper {
    display: flex; 
    flex-wrap: wrap;
  }
</style>