<script setup>
  const name = "Evento Click";
  // método, puede tener atributos o no
  const handleClick = message => {
    console.log(message);
  }
</script>

<template>
  <section id="eventoclick">
    <h1>{{ name.toUpperCase() }}</h1>
    <button v-on:click.right.prevent="handleClick('Texto Derecho')">Click Derecho</button>
    <button @click="handleClick('Texto Izquierdo')">Click Izquierdo</button>
    <button @click.middle="handleClick('Texto Centro')">Click Centro</button>
  </section>
</template>

<style scope>
  section {
    margin-top: 20px;
  }

  h1{
    font-family: Arial, sans-serif;
  }
</style>