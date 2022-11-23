<template>
  <form @submit.prevent="getData" class="row g-3 justify-content-center">
    <div class="col-auto">
      <input
        v-model.trim="busqueda"
        class="form-control"
        type="text"
        name=""
        id=""
      />
    </div>
    <div class="col-auto">
      <button class="btn btn-primary mb-3" type="submit">Buscar</button>
    </div>
  </form>
</template>

<script>
export default {
  data: () => ({
    busqueda: "",
  }),
  methods: {
    getData() {
      this.$emit("buscar", this.busqueda);
      this.busqueda = "";
    },
  },
};
</script>

<style></style>
