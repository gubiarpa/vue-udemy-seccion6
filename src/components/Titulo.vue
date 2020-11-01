<template>
  <h1>{{texto}}</h1>
</template>

<script>
export default {
    props: {
        texto: {
          type: String,
          default: 'Título Principal'
        }
    }
}
</script>

<style>

</style>