<template>
    <div>
        <p>{{movieTitle}}</p>
        <p>{{tvTitle}}</p>
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