<script setup>
  const hola = 'Hola Mundo'
  const styleColor = "color: blue"
  const arrayColores = ["blue", "red", "violet"]
  const activo = true
</script>
<!-- v-bind:  sirve para atributos o se reemplaza por : -->
<template>
  <h1>
    {{hola}}
  </h1>
  <h2 v-bind:style = "styleColor">Soy Azul</h2>
  <h2>{{ arrayColores }}</h2>
  <h2 :style = "`color: ${arrayColores[1]}`">ejemplo colores </h2>
  <h2>{{ activo ? "activo" : "inactivo" }}</h2>
</template>

<style>

</style>