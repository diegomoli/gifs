<template>
  <nav-bar />
  <div class="container mt-3 text-center">
    <router-view />
  </div>
  >
</template>

<script>
import NavBar from "./components/NavBar.vue";
export default {
  components: { NavBar },
};
</script>

<style scoped>
div {
  border-radius: 13px;
  box-shadow: 3px 3px 7px #ccc;
  padding: 1rem;
}
</style>
