<script setup>
import { ref } from 'vue';

let num = ref(0)

</script>

<template>
  <!-- NAVBAR -->
  <nav class="navbar navbar-expand-lg navbar-dark bg-primary">
    <div class="container-fluid">

      <router-link class="navbar-brand" to="/">
      <img src="./assets/pokeball.png" alt="Logo" width="30" height="24" class=".d-inline-block .align-text-top">
      Pokedex
    </router-link>

      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavDropdown"
        aria-controls="navbarNavDropdown" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNavDropdown">
        <ul class="navbar-nav">
          <li class="nav-item">
            <router-link class="nav-link" to="/">Home>
            </router-link>
          </li>
          <!-- <li class="nav-item">
            <router-link class="nav-link" to="/about">Sobre>
            </router-link>
          </li> -->

        </ul>
      </div>
    </div>
  </nav>

  <!-- CONTENT -->
  <div class="main">
    <router-view></router-view>
  </div>

  <footer class="bg-primary text-light">
    <div>Rogerio Pessanha - {{ new Date().getFullYear() }}</div>
  </footer>
</template>

<style>
footer{
  position: fixed;
  bottom: 0;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 56px;
}
</style>