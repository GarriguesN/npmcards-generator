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
<div class="h-min-full h-max-fit bg-slate-700">
    <StartView v-if="isStarting" />

    <RouterView v-else/>
</div>
  
</template>

<style scoped>

</style>
