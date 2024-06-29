<template>
  <section id="estado">
    <h2>{{ activo ? "activo" : "inactivo" }}</h2>
    <h2 v-if="activo === true">Activo</h2>
    <h2 v-else-if="activo === false">Inactivo</h2>
    <h2 v-else>Indeciso</h2>
    <p v-show="activo">Show - le pone display none</p>
  </section>
</template>

<script setup>
  const activo = true
</script>

<style scoped>
  section {
    margin-top: 20px;
  }

  h1, h2 {
    font-family: Arial, sans-serif;
  }
</style>