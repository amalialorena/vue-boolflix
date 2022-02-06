<template>
  <div class="container">
    <div class="card">
      <Poster :poster="movie.poster_path" :backdrop="movie.backdrop_path" />
      <div class="info-card">
        <Title :movieTitle="movie.title" :tvTitle="movie.name" />
        <OriginalTitle
          :movieTitle="movie.original_title"
          :tvTitle="movie.original_name"
        />
        <Ratings :vote="movie.vote_average" />
        <Overview :summary="movie.overview" />
      </div>
    </div>
  </div>
</template>

<script>
import Title from "./Title.vue";
import OriginalTitle from "./OriginalTitle.vue";
import Poster from "./Poster.vue";
import Ratings from "./Ratings.vue";
import Overview from "./Overview.vue";

export default {
  name: "Card",
  components: {
    Poster,
    Title,
    OriginalTitle,
    Ratings,
    Overview,
  },
  props: {
    movie: [Array, Object],
  },
  data: function () {
    return {
      language: "it",
    };
  },
  computed: {
    movieLanguage: function () {
      return this.language;
    },
  },
};
</script>

<style scoped lang="scss">
.container {
  width: calc((100%) - 20px);
  margin: 10px;

  @media (min-width: 340px) {
    width: calc((100% / 2) - 20px);
    margin: 10px;
  }

  @media (min-width: 576px) {
    width: calc((100% / 4) - 20px);
    margin: 10px;
  }

  @media (min-width: 992px) and (max-width: 1200px) {
    width: calc((100% / 6) - 20px);
    margin: 10px;
  }

  @media (min-width: 1200px) {
    width: calc((100% / 8) - 20px);
    margin: 10px;
  }

  h2 {
    color: white;
    width: 100%;
  }

  .card {
    width: 100%;
    height: 100%;
    position: relative;
  }

  .info-card {
    display: none;
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    z-index: 1;
    width: 100%;
    background-color: rgba(36, 34, 34, 0.959);
    color: white;
    font-size: 14px;
    padding: 5px;
  }

  .card:hover .card {
    background-color: grey;
  }
  
  .card:hover .info-card {
    display: block;

    * {
      display: -webkit-box;
      overflow: hidden;
      text-overflow: ellipsis;
      -webkit-line-clamp: 5;
      -webkit-box-orient: vertical;
    }
  }
}
</style>

