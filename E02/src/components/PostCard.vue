<script lang="ts" setup>
import PostButton from './PostButton.vue';
</script>

<template>
    <div class="post-card">
        <h3>Titulo</h3>
        <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Rerum nostrum, laudantium nulla vero tenetur non id
            velit doloremque deserunt beatae dolorem, molestiae quidem culpa expedita, fugiat repellendus provident
            consectetur sit!</p>

        <PostButton />
    </div>
</template>

<style scoped>
.post-card {
    border-radius: 15px;
    padding: 10px;
    margin: 5px;
    border: 1px solid #ccc;
}
</style>