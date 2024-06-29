<script setup>
  const styleColor = "color: blue"
  const arrayColores = ["blue", "red", "violet"]
</script>

<template>
  <section id="colores">
    <h2 v-bind:style="styleColor">Soy Azul</h2>
    <h2>Array de Colores: {{ arrayColores }}</h2>
    <h2 :style="`color: ${arrayColores[1]}`">Ejemplo Colores</h2>
  </section> 
</template>

<style scoped>
  h2 {
    font-family: Arial, sans-serif;
  }

  section {
    margin-top: 20px;
  }
</style>