<script setup lang="ts">
const hasError = false
</script>

<template>
    <p :class="{ 'danger': hasError, 'success': !hasError }">{{ hasError ? 'Ocurrio un error' : 'Todo correcto' }}</p>
    <p :style="{ color: hasError ? 'red' : 'green' }">{{ hasError ? 'Ocurrio un error' : 'Todo correcto' }}</p>
</template>

<style scoped>
.danger {
    color: red
}

.success {
    color: green
}
</style>