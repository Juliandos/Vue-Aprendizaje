<script setup>
  // import VueRouter from 'vue-router'
  import { ref, computed } from 'vue'
  import HolaMundo from './components/Aprendizaje/HolaMundo.vue'
  import VBind from './components/Aprendizaje/VBind.vue'
  import VIf from './components/Aprendizaje/VIf.vue'
  import VFor from './components/Aprendizaje/VFor.vue'
  import EventoClick from './components/Aprendizaje/EventoClick.vue'
  import ReactividadContador from './components/Aprendizaje/ReactividadContador.vue'
  import Tags from './components/Tags/InputTag.vue'
  import DragDrop from './components/DragDrop/Todo.vue'
  import Propina from './components/Propina/TipView.vue'
  import Menu from './components/Menu/Menu.vue'
  import Reader from './components/Reader/RSSReader.vue'

  const routes = {
  '/': HolaMundo,
  '/colores': VBind,
  '/estado': VIf,
  '/lista-de-colores': VFor,
  '/eventoclick': EventoClick,
  '/reactividad': ReactividadContador,
  '/tags': Tags,
  '/dragdrop': DragDrop,
  '/propina': Propina,
  '/menu': Menu,
  '/reader': Reader

}

const currentPath = ref(window.location.hash)

window.addEventListener('hashchange', () => {
  currentPath.value = window.location.hash
})

const currentView = computed(() => {
  return routes[currentPath.value.slice(1) || '/'] 
})
</script>

<template>

  <a href="#/">Home</a> |
  <a href="#/colores">Colores</a> |
  <a href="#/estado">Estado</a> |
  <a href="#/lista-de-colores">Lista Colores</a> |
  <a href="#/eventoclick">Evento Click</a> |
  <a href="#/reactividad">Reactividad</a> |
  <a href="#/tags">Tags</a> |
  <a href="#/dragdrop">DragDrop</a> |
  <a href="#/propina">Propina</a> |
  <a href="#/menu">Menu</a> |
  <a href="#/reader">Reader</a> 
  <component :is="currentView" />
  

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
