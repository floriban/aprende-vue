<script setup lang="ts">
import { ref, type Ref } from 'vue';

const color: Ref = ref("black")

const cambiarColor = (): void => {
    color.value = "blueviolet"
}
</script>

<template>
    <p :style="{ backgroundColor: '#ccc', color: color }">Lorem ipsum dolor sit amet consectetur
        adipisicing elit. Veritatis
        dolor mollitia nemo earum assumenda rerum
        autem deleniti excepturi veniam ipsa quia, omnis perspiciatis maxime consectetur ab necessitatibus
        exercitationem. Quidem, sapiente.</p>

    <button @click="cambiarColor()">Cambiar color</button>
</template>