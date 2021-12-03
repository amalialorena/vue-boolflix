<template>
    <div>
        <p>{{movieTitle}}</p>
        <p>{{tvTitle}}</p>
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
