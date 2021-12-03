<template>
    <div>
        <h1>{{movieTitle}}</h1>
        <h1>{{tvTitle}}</h1>
    </div>
</template>

<script> 

export default {
    name: 'Title',
    props: {
        movieTitle: String,
        tvTitle: String
    }
}


</script>

<style scoped lang="scss">

</style>