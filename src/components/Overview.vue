<template>
    <div class="review-text" v-if="summary">
        <p><strong>Overview:</strong>{{summary}}</p>
    </div>
</template>

<script>
export default {
  name: 'Overview',
  props: {
      summary: String
  }
}
</script>

<style scoped lang="scss">

</style>