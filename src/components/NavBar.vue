<template>
  <nav class="navbar navbar-expand-lg bg-dark navbar-dark">
    <div class="container-fluid">
      <a class="navbar-brand border border-info p-2" href="/"> Gifs </a>
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarNav"
        aria-controls="navbarNav"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav">
          <li class="nav-item">
            <router-link
              class="nav-link"
              active-class="bg-info text-dark fw-bold"
              to="/"
              >Home</router-link
            >
          </li>
          <li class="nav-item">
            <router-link
              class="nav-link"
              active-class="bg-info text-dark fw-bold"
              to="/gifs"
              >Gifs</router-link
            >
          </li>
          <li class="nav-item">
            <router-link
              class="nav-link"
              active-class="bg-info text-dark fw-bold"
              to="/stickers"
              >Stickers</router-link
            >
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {};
</script>

<style></style>
