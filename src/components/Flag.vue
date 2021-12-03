<template>
  <div class="flag" v-if="this.language === 'it'">
    <img src="../assets/img/italy.png" alt="" />
  </div>
  <div class="flag" v-else-if="this.language === 'en'">
    <img src="../assets/img/united-states-of-america.png" alt="" />
  </div>
  <div class="flag" v-else-if="this.language === 'de'">
    <img src="../assets/img/germany.png" alt="" />
  </div>
  <div class="flag" v-else>
    <img src="../assets/img/rainbow-flag.png" alt="" />
  </div>
</template>

<script>
export default {
  name: "Flag",
  props: {
    language: String,
  },
};
</script>

<style scoped lang="scss">
.flag {
  width: 50px;
  height: 40px;
  img {
    height: 100%;
  }
}
</style>