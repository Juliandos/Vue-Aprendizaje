<template>
  <section id="lista-de-colores">
    <ul>
      <li v-for="(color, index) in arrayColores" :key="index">
        {{ index }} - {{ color }}
      </li>
    </ul>
  </section>

  <!-- el v-if puede ir con el v-for pero tiene que ir antes o como se muestra en el span posterior, el template hace que se renderize condicionalmente-->

  <section id="lista-de-frutas">
    <ul>
      <template v-for="(fruta, index) in arrayFrutas" :key="index">
        <li v-if="fruta.precio > 1">
          {{ index }} - {{ fruta.nombre }} - {{ fruta.precio }} - {{ fruta.descripcion }}
        </li>
      </template>
    </ul>
  </section>
</template>

<script setup>
  const arrayColores = ["blue", "red", "violet"]
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

<style scoped>
  section {
    margin-top: 20px;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

  li {
    margin: 5px 0;
  }
</style>