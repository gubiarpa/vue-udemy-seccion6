<template>
  <Titulo texto="Tîtulo de mi Blog" />
  <button @click="consumirApi">Consumir API</button><br>
  <select>
    <option :value="item.id" v-for="item in arrayBlog" :key="item.id">{{ item.title }}</option>
  </select>
</template>

<script>
import Titulo from "../components/Titulo";
export default {
    components: {
        Titulo
    },
    data() {
      return {
        arrayBlog: []
      }
    },
    methods: {
      async consumirApi() {
        try {
          const data = await fetch('http://jsonplaceholder.typicode.com/posts'); // traemos de la API
          const array = await data.json(); // configuramos
          this.arrayBlog = array;
        } catch (error) {
          console.log(error);
        }
      }
    }
}
</script>

<style>

</style>