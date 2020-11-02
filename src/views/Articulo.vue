<template>
  <Titulo texto="Ruta con parámetros" />
  <h2>{{ $route.params.id }}</h2>
</template>

<script>
import Titulo from "../components/Titulo";
export default {
    components: {
        Titulo
    }
}
</script>

<style>

</style>