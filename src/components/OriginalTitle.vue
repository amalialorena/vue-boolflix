<template>
    <div>
        <p v-if="movieTitle"> <strong>Titolo originale: </strong> {{movieTitle}}</p>
        <p v-if="tvTitle"> <strong>Titolo originale: </strong> {{tvTitle}}</p>
    </div>
</template>

<script>


export default {
   name: 'OriginalTitle',
   props: {
       movieTitle: String,
       tvTitle: String
   }
}
</script>
