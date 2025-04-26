<script setup lang="ts">
import { ref, type Ref } from 'vue';

const inputText: Ref<string> = ref('')
const acepto: Ref<boolean> = ref(true)
const select: Ref<string> = ref('f')
const radio: Ref<string> = ref('wifi')
</script>

<template>
    <form action="">
        <input type="text" v-model="inputText">
        <input type="checkbox" v-model="acepto"> Acepto los terminos

        <input type="radio" name="conexion" value="wifi" v-model="radio"> WIFI
        <input type="radio" name="conexion" value="red" v-model="radio"> Red

        <select name="" id="" v-model="select">
            <option value="m">Masculino</option>
            <option value="f">Femenino</option>
        </select>
    </form>
    <h3>{{ inputText }}</h3>
</template>

<style scoped></style>