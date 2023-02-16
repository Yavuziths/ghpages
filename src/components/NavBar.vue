<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>
<template>
  <!-- here is navbar with bootstrap-->
  <nav class="navbar bg-body-tertiary fixed-top">
    <div class="container-fluid">
      <RouterLink class="navbar-brand" to="/">MajorLeagues</RouterLink>
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="offcanvas"
        data-bs-target="#offcanvasNavbar"
        aria-controls="offcanvasNavbar"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div
        class="offcanvas offcanvas-end"
        tabindex="-1"
        id="offcanvasNavbar"
        aria-labelledby="offcanvasNavbarLabel"
      >
        <div class="offcanvas-header">
          <h5 class="offcanvas-title" id="offcanvasNavbarLabel">
            MajorLeagues
          </h5>
          <button
            type="button"
            class="btn-close"
            data-bs-dismiss="offcanvas"
            aria-label="Close"
          ></button>
        </div>
        <div class="offcanvas-body">
          <ul class="navbar-nav justify-content-end flex-grow-1 pe-3">
            <li class="nav-item">
              <RouterLink class="nav-link active" aria-current="page" to="/"
                >Home</RouterLink
              >
            </li>
            <li class="nav-item">
              <RouterLink class="nav-link" to="/team">Team</RouterLink>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </nav>
  <RouterView />
</template>

<!-- Some navbar css -->
<style scoped>
.navbar {
  background: linear-gradient(
    to bottom,
    rgba(3, 3, 3, 0.7) 0%,
    rgba(255, 0, 0, 0)
  );
}

.offcanvas-title {
  color: orangered;
}

.navbar-brand {
  color: orangered;
}

.navbar-brand:hover {
  color: white;
}

.navbar-toggler {
  background-color: white;
}

.navbar-nav .nav-link:hover {
  color: white;
  background-color: orangered;
}

.page {
  color: yellow;
}
</style>
