<template>
  <div class="hello">
    <input type="text" v-model="userMovie">
    <button @click.prevent="$emit('info', userMovie)">Search</button>
  
  </div>
</template>

<script>
export default {
  name: 'Search',
  props: {
    
  },
  data () {
    return {
      userMovie: "",
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
