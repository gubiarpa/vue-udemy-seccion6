<template>
  <Titulo texto="Tîtulo de mi Blog" />
  <button @click="consumirApi">Consumir API</button><br>
  <div v-for="item in arrayBlog" :key="item.id">
    <router-link :to="`/blog/${item.id}`">
      {{ item.title }}
    </router-link>
  </div>
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
    },
    created() {
      this.consumirApi();
    }
}
</script>

<style>

</style>