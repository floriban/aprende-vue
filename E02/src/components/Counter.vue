<template>
    <h3>{{ counter }}</h3>
    <button @click="addCounter">Incrementar</button>
</template>

<script setup lang="ts">
import { ref, type Ref } from 'vue';

let counter: Ref = ref(0)
const addCounter = (): void => {
    counter.value++
}
</script>