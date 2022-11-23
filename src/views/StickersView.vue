<template>
  <h1>Search Stickers</h1>

  <search @buscar="getStickers" />
  <spinner v-if="loading" />

  <div class="row">
    <div
      v-for="sticker in stickers"
      :key="sticker.id"
      class="col-12 col-md-4 g-2"
    >
      <card :gif="sticker" />
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
    stickers: [],
    loading: true,
  }),
  created() {
    this.getStickers();
  },
  methods: {
    async getStickers(busqueda = "pokemon") {
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
        `https://api.giphy.com/v1/stickers/search?api_key=R8SIbnO8v5TPIzf6fzpFp0mIo7iVLZ0i&q=${busqueda}`
      );
      const { data } = await resp.json();
      this.stickers = data;
      this.loading = false;
    },
  },
  components: { Card, Search, Spinner },
};
</script>
