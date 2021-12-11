<template>
  <nav>
    <div class="container">
      <h1>BOOLFLIX</h1>
      <div>
        <input type="text" v-model="userMovie" v-on:keyup.enter="$emit('info', userMovie)">
        <button @click.prevent="$emit('info', userMovie)">Search</button>
      </div>
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
    
    .container {
      display: flex;
      justify-content: space-between;
      align-items: center;
      height: 100%;
      margin: auto; 
      margin-left: 10px;
      margin-right: 10px;
    }
    h1 {
      color: red;
    }
  }

</style>
