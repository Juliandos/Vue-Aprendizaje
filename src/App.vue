<script setup>
  const hola = 'Hola Mundo'
  const styleColor = "color: blue"
  const arrayColores = ["blue", "red", "violet"]
  const activo = true
  const arrayFrutas = [
  {
    "nombre": "Manzana",
    "precio": 1.2,
    "descripcion": "Una fruta crujiente y dulce, rica en fibra y vitamina C."
  },
  {
    "nombre": "Plátano",
    "precio": 0.5,
    "descripcion": "Una fruta suave y dulce, rica en potasio y excelente para la energía rápida."
  },
  {
    "nombre": "Naranja",
    "precio": 0.8,
    "descripcion": "Una fruta cítrica y jugosa, conocida por su alto contenido de vitamina C."
  },
  {
    "nombre": "Fresa",
    "precio": 2.0,
    "descripcion": "Una fruta pequeña y jugosa, con un sabor dulce y ácido, rica en antioxidantes."
  },
  {
    "nombre": "Uva",
    "precio": 3.0,
    "descripcion": "Frutas pequeñas y dulces, disponibles en variedades verdes y moradas, ricas en antioxidantes."
  }
]

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
  <h2 v-if="activo === true">Activo</h2>
  <h2 v-else-if="activo === false">Inactivo</h2>
  <h2 v-else>Indeciso</h2>
  <p v-show="activo">Show - le pone display none</p>
  <ul>
    <li
      v-for="(color, index) in arrayColores"
      :key="index"
    >
    {{ index }} - {{ color }}
    </li>
  </ul>
  <!-- el v-if puede ir con el v-for pero tiene que ir antes o como se muestra en el span posterior, el template hace que se renderize condicionalmente-->
  <ul>
    <template
      v-for="(fruta, index) in arrayFrutas"
      :key="index">
      <li v-if="fruta.precio > 1">
        {{ index }} - {{ fruta.nombre }} - {{ fruta.precio }} - {{ fruta.descripcion }}
      </li>
    </template>
  </ul>
</template>

<style>

</style>