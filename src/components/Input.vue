<script setup>
import { ref, defineProps, defineEmits, watch } from 'vue';
import ColorPicker from "@/components/ColorPicker.vue";

const props = defineProps({
  label: {
    type: String,
    required: true
  },
  idCheckbox: {
    type: String,
    required: true
  },
  ids: {
    type: String,
    required: true
  },
  info: {
    type: String,
    required: true
  },
  placeholder: {
    type: String,
    required: true
  },
  modelValue: {
    type: Object,
    required: true
  },
  colorPicker: {
    type: String,
    default: '#41B883'
  }
});

const emit = defineEmits(['update:modelValue']);

const checkboxValue = ref(true);
const colorValue = ref(props.colorPicker);

watch([checkboxValue, colorValue], () => {
  emit('update:modelValue', {
    text: props.modelValue.text,
    checkbox: checkboxValue.value,
    color: colorValue.value
  });
});

const handleInput = (event) => {
  emit('update:modelValue', {
    text: event.target.value,
    checkbox: checkboxValue.value,
    color: colorValue.value
  });
};
</script>

<template>
  <div :id="ids">
    <label :for="ids" class="block mb-2 text-sm font-medium">{{label}}</label>
    <div class="flex">
      <div class="flex items-center me-4">
        <input
          v-model="checkboxValue"
          :id="idCheckbox"
          type="checkbox"
          class="w-4 h-4 accent-green-500 text-green-600 bg-gray-100 border-gray-300 rounded focus:ring-green-500 dark:focus:ring-green-600 dark:ring-offset-gray-800 focus:ring-2 dark:bg-gray-700 dark:border-gray-600"
        >
      </div>
      <span
        class="inline-flex items-center px-3 text-sm bg-gray-700 rounded-s-lg border-t border-l border-b border-[#41B883]"
      >
        <div v-if="info === 'name'">
          <svg class="w-4 h-4 text-gray-500 dark:text-gray-400" aria-hidden="true" xmlns="http://www.w3.org/2000/svg"
            fill="currentColor" viewBox="0 0 20 20">
            <path
              d="M10 0a10 10 0 1 0 10 10A10.011 10.011 0 0 0 10 0Zm0 5a3 3 0 1 1 0 6 3 3 0 0 1 0-6Zm0 13a8.949 8.949 0 0 1-4.951-1.488A3.987 3.987 0 0 1 9 13h2a3.987 3.987 0 0 1 3.951 3.512A8.949 8.949 0 0 1 10 18Z" />
          </svg>
        </div>
        <div v-else>
          {{info}}
        </div>
      </span>
      <input
        type="text"
        :id="ids"
        :value="props.modelValue.text"
        @input="handleInput"
        class="rounded-none rounded-e-lg text-gray-200 border border-[#41B883] caret-[#41B883] focus:border-[#41B883] focus:ring-[#41B883] bg-gray-800 flex-1 text-sm p-2.5"
        :placeholder="placeholder"
      >
      <div class="flex items-center ml-2">
        <ColorPicker v-model="colorValue"></ColorPicker>
      </div>
    </div>
  </div>
</template>

<style scoped>
</style>
