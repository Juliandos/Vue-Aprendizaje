<script setup>
  import {computed, ref} from 'vue'

  const name = 'Reactividad con Contador';
  const contador = ref(0);
  const arrayFavoritos = ref([]);

  const incrementar = () => {
    contador.value++;
  }
  const decrementar = () => {
    contador.value--;
  }
  const resetear = () => {
    contador.value = 0;
  }
  const contadorDeClase = computed( () => {
    if (contador.value === 0) {
      return ''
    }
    if (contador.value > 0) {
      return 'positivo'
    }
    if (contador.value < 0) {
      return 'negativo'
    }
  })

  const agregar = () => {
    arrayFavoritos.value.push(contador.value)
  }

  const bloquearBtnAgregar = computed(() => {
    const numSearch = arrayFavoritos.value.find((num) => num === contador.value)
    // if(numSearch === 0) return true;
    // return numSearch ? true : false;
    return numSearch || numSearch === 0;
  })
</script>
<!-- ref te devuelve un objeto y hay que acceder a el mediante un ., cuando muta cambia automáticamente, también se utiliza una constante. -->
<template>
  <section id="reactividadcontador">
    <h1> {{ name }}</h1>
    <!-- podría haber hecho esto //:class="contador > 0 ? 'positivo' : contador < 0 ? 'negativo' : ''", pero es mejor con computed -->
    <h2 :class="contadorDeClase">{{ contador }}</h2>
    <button @click = "incrementar">Aumentar</button>
    <button @click = "decrementar">Disminuir</button>
    <button @click = "resetear">Resetear</button>
    <button @click = "agregar" :disabled="bloquearBtnAgregar">Agregar</button>
    <br>
    {{ arrayFavoritos }}
  </section>
</template>

<style scoped>
  .positivo{
    color: green;
  }

  .negativo{
    color: red;
  }

  h1, h2 {
    font-family: Arial, sans-serif;
  }

  section {
    margin-top: 20px;
  }
</style>