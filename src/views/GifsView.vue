<template>
  <h1>Search Gifs</h1>

  <search @buscar="getGifs" />
  <Spinner v-if="loading" />
  <div class="row">
    <div v-for="gif in gifs" :key="gif.id" class="col-12 col-md-4 g-2">
      <card :gif="gif" />
    </div>
  </div>
</template>
<script>
import Card from "../components/Card.vue";
import Search from "../components/Search.vue";
import Spinner from "../components/Spinner.vue";
import Swal from "sweetalert2";

export default {
  data: () => ({
    gifs: [],
    loading: true,
  }),
  created() {
    this.getGifs();
  },
  methods: {
    async getGifs(busqueda = "pokemon") {
      if (busqueda.trim() === "") {
        return Swal.fire({
          icon: "error",
          title: "Oops...",
          text: "El campo no puede estar vacio!",
          timer: 4000,
          timerProgressBar: true,
        });
      }
      this.loading = true;
      const resp = await fetch(
        `https://api.giphy.com/v1/gifs/search?api_key=R8SIbnO8v5TPIzf6fzpFp0mIo7iVLZ0i&q=${busqueda}`
      );
      const { data } = await resp.json();
      this.gifs = data;
      this.loading = false;
    },
  },
  components: { Card, Search, Spinner },
};
</script>
