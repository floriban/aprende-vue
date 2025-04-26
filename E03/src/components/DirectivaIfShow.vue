<script setup lang="ts">
let age = 12
</script>

<template>
    <!-- CON V-IF -->
    <h1 v-if="age < 18">Eres menor de edad</h1>
    <h1 v-else>Eres mayor de edad</h1>

    <!-- CON V-SHOW -->
    <h1 v-show="age < 18">Eres menor de edad</h1>
    <h1 v-show="age >= 18">Eres mayor de edad</h1>
</template>