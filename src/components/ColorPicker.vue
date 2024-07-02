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
            class="color-picker"
        >
    </label>
</template>

