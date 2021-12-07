<template>
    <div>
        <p v-if="movieTitle"><strong>Titolo: </strong>{{movieTitle}}</p>
        <p v-if="tvTitle"><strong>Titolo: </strong>{{tvTitle}}</p>
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

