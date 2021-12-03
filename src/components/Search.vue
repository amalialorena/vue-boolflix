<template>
  <nav>
    <h1>BOOLFLIX</h1>
    <div>
      <input type="text" v-model="userMovie">
      <button @click.prevent="$emit('info', userMovie)">Search</button>
    </div>
  </nav>
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
  nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 80px;
    background-color: black;
    h1 {
      color: red;
    }
  }

</style>
