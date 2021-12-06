<template>
    <div>
        <p>{{summary}}</p>
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
