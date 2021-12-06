<template>
  <div>
    <div v-if="poster == null">
      <img src="../assets/img/italy.png" />
    </div>
    <div v-else>
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
</style>