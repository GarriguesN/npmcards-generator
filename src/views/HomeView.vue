<script setup>
import { ref } from 'vue';
import Form from "@/components/Form.vue";
import StarsBackground from "@/components/StarsBackground.vue";
import Preview from "@/components/Preview.vue";

const formData = ref({
  name: {
    text: '',
    checkbox: true,
    color: '#4ADE80'
  },
  username: {
    text: '',
    checkbox: true,
    color: '#D1D5DB'
  },
  npm: {
    text: '',
    checkbox: true,
    color: '#EF4444'
  },
  github: {
    text: '',
    checkbox: true,
    color: '#4ADE80'
  },
  linkedin: {
    text: '',
    checkbox: true,
    color: '#60A5FA'
  },
  wakatime: {
    text: '',
    checkbox: true,
    color: '#9CA3AF'
  },
  package: {
    text: '',
    checkbox: true,
    color: '#DC2626'
  },
  otherOptions: {
    enableBottomInfo: true,
    backgroundColor: '#282C34',
    borderBoxColor: '#4ADE80'
  }
});

const updateFormData = (data) => {
  formData.value = data;
};
</script>

<template>
  <div id="content" class="flex-grow flex h-full">
    <div id="col1" class="flex flex-1 justify-center items-center">
      <StarsBackground/>
      <Form @update:formData="updateFormData"></Form>
    </div>

    <div id="col2" class="flex flex-col flex-1 border-l-2 w-full justify-center items-center align-middle border-green-700">
      <h1 class=" text-3xl font-mono ">NPX CARD PREVIEW</h1>
      <p class="mb-10 text-sm font-mono">This is a basic preview and may look different depending on your terminal</p>
      <Preview :formData="formData"></Preview>
    </div>
  </div>
</template>
