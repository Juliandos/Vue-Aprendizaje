<script setup>
  import HolaMundo from './components/HolaMundo.vue'
  import VBind from './components/VBind.vue'
  import VIf from './components/VIf.vue'
  import VFor from './components/VFor.vue'
  import EventoClick from './components/EventoClick.vue'
</script>

<template>
  <nav>
    <ul>
      <li><a href="#hola-mundo">Hola Mundo</a></li>
      <li><a href="#colores">Colores</a></li>
      <li><a href="#estado">Estado</a></li>
      <li><a href="#lista-de-colores">Lista de Colores</a></li>
      <li><a href="#lista-de-frutas">Lista de Frutas</a></li>
    </ul>
  </nav>

  <HolaMundo/>

  <VBind/>

  <VIf/>

  <VFor/>

  <EventoClick/>

</template>

<style>
  nav ul {
    list-style-type: none;
    padding: 0;
  }

  nav li {
    display: inline;
    margin-right: 10px;
  }

  nav a {
    text-decoration: none;
    color: blue;
    font-weight: bold;
  }
</style>
