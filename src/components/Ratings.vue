<template>
  <div>
    <div class="stars">
      <p><strong>Voto:</strong></p>
      <div class="star filled-star" v-for="star, i in numberOfStars" :key="`${i}-filled`">
        <i class="fas fa-star"></i>
      </div>
      <div class="star hollow-star" v-for="hollowStar, j in hollowStars" :key="`${j}-hollow`">
        <i class="fas fa-star"></i>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Ratings",
  props: {
    vote: Number,
  },
  computed: {
    numberOfStars: function () {
      let divideVote = Math.round(this.vote / 2);
      return divideVote;
    },
    hollowStars: function () {
      let hollowStars = 5 - this.numberOfStars;
      return hollowStars;
    },
  },
}
</script>

<style scoped lang="scss">
.stars {
  display: flex;
  .star {
    i {
      text-shadow: 0 0 1px #745f03;
    }
  }
  .filled-star i {
    color: rgb(255, 208, 0);
  }
  .hollow-star i {
    color: rgb(201, 199, 199);
  }
}
</style>