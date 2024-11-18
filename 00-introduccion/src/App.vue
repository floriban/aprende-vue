<template>
  <h1>{{ saludo }}</h1>
  <span v-html="btnHtml"></span>
  <p :style="color">Cambio de color</p>

  <p v-if="puntajeCrediticio >= 900">Excelente CLIENTE 😍</p>
  <p v-else-if="puntajeCrediticio < 900 && puntajeCrediticio >= 700">CLIENTE Regular 🙂</p>
  <p v-else>Mal CLIENTE 😭</p>

  <p v-show="puntajeCrediticio >= 900">TEST</p>

  <ul>
    <li v-for="(lenguaje, index) in lenguajes" :key="index">{{ lenguaje }}</li>
  </ul>
</template>

<script setup lang="ts">
const saludo = 'Hola a todos 2'
const btnHtml = '<button>Mi Boton</button>'
const color = "color: red"

const puntajeCrediticio = 900

const lenguajes = [
  "JavaScript",
  "Python",
  "Java",
  "C#",
  "C++",
  "Ruby",
  "PHP",
  "Swift",
  "Go",
  "Kotlin",
  "TypeScript",
  "Rust",
  "Perl",
  "R",
  "Scala",
  "Dart",
  "Lua",
  "Haskell",
  "Elixir",
  "Clojure"
];

</script>

<style scoped>
h1 {
  font-size: 80px;
}
</style>
