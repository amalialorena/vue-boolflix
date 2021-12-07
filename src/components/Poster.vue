<template>
  <div class="poster-container">
    <div class="poster" v-if="poster == null">
      <img src="../assets/img/netflix-natale.jpeg" />
    </div>
    <div class="poster" v-else>
      <img
        :src="`https://image.tmdb.org/t/p/w342/${poster}`"
        alt="movie poster"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: "Poster",
  props: {
    poster: String,
  },
};
</script>

<style scoped lang="scss">
  .poster-container {
    height: 100%;
    .poster{
      height: 100%;
      img {
      height: 100%;
      width: 100%;
      object-fit: cover;
    }
  }   
}
</style>