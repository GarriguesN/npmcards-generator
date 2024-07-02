<script setup>
import { RouterLink, RouterView } from 'vue-router'
import { ref } from 'vue';
import StartView from './views/StartView.vue';

const isStarting = ref(true);

setTimeout(() => {
    isStarting.value = false;
}, 1000);

</script>

<template>
<div class="flex flex-col min-h-[100dvh] w-screen">
    <StartView v-if="isStarting" />

    <RouterView v-else/>
</div>
  
</template>

<style scoped>

</style>
