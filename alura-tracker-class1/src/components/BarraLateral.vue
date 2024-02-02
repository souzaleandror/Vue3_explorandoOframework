<template>
  <header>
    <h1 class="is-flex is-align-items-center is-justify-content-space-around">
      <img src="../assets/logo_alura.png" alt="" />
    </h1>
  </header>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'BarraLateral'
});
</script>

<style>
/* Todo o estilo do componente */
header {
  background: #0d3b66;
  width: 100%;
  height: 100vh;
  padding: 1rem;
}

@media only screen and (max-width: 768px) {
  header {
    padding: 2.5rem;
    height: auto;
  }
}
</style>