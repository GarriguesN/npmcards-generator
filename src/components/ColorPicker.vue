<!-- ColorPicker.vue -->
<script setup>
import { defineProps, defineEmits } from 'vue';

const props = defineProps({
    label: {
        type: String,
        default: "Choose a color"
    },
    modelValue: {
        type: String,
        default: "#41B883"
    }
});

const emit = defineEmits(['update:modelValue']);

const handleChange = (event) => {
    emit('update:modelValue', event.target.value);
};
</script>

<template>
    <label>
        <input
            type="color"
            class="bg-transparent outline-none w-[400%]"
            :value="modelValue"
            @input="handleChange"
        >
    </label>
</template>

