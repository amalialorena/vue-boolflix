<template>
  <nav>
    <h1>BOOLFLIX</h1>
    <div class="search-container">
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
    height: 80px;
    background-color: black;
    display: flex;
    justify-content: space-between;
    align-items: center;
    h1 {
      color: red;
    }
  }

</style>
