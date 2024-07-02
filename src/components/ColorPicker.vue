<script setup>
import { defineProps } from 'vue';

const props = defineProps({
    label: {
        type: String,
        default: "Choose a color"
    }
});
</script>


<template>
    <label>
        <input
            type="color"
            class="bg-transparent outline-none w-[400%]"
            value="#41B883"
        >
    </label>
</template>

<style>

</style>