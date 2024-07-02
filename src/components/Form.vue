<script setup>
import { ref, watch, defineEmits, defineProps } from 'vue';
import Input from "@/components/Input.vue";
import Button from "@/components/Button.vue";
import ColorPicker from './ColorPicker.vue';

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

const emit = defineEmits(['update:formData']);

watch(formData, (newFormData) => {
  emit('update:formData', { ...newFormData });
}, { deep: true });

const handleSubmit = (event) => {
  event.preventDefault();
  console.log('Send it!');
};
</script>

<template>
  <form class="w-[70%] space-y-5" @submit="handleSubmit">
    <div class="flex justify-between">
      <Input v-model="formData.name" ids="nameInput" idCheckbox="nameCheckbox" label="Your name!" info="name" placeholder="Your name" :colorPicker="'#4ADE80'"/>
      <Input v-model="formData.username" ids="usernameInput" idCheckbox="usernameCheckbox" label="Your username!" info="@" placeholder="Your username" :colorPicker="'#D1D5DB'" />
    </div>
    <Input v-model="formData.npm" ids="npmInput" idCheckbox="npmCheckbox" label="Your npm username!" info="https://npmjs.com/~" placeholder="npmuser" :colorPicker="'#EF4444'" />
    <Input v-model="formData.github" ids="githubInput" idCheckbox="githubCheckbox" label="Your github tag!" info="https://github.com/" placeholder="githubtag" :colorPicker="'#4ADE80'" />
    <Input v-model="formData.linkedin" ids="linkedinInput" idCheckbox="linkedinCheckbox" label="Your LinkedIn Url Tag!" info="https://www.linkedin.com/in/" placeholder="linkedinurl" :colorPicker="'#60A5FA'" />
    <Input v-model="formData.wakatime" ids="wakatimeInput" idCheckbox="wakatimeCheckbox" label="Your wakatime user!" info="https://wakatime.com/" placeholder="wakatimename" :colorPicker="'#9CA3AF'" />
    <Input v-model="formData.package" ids="cardInput" idCheckbox="cardCheckbox" label="Your package name (check it's available!)" info="npx" placeholder="Name of the package" :colorPicker="'#DC2626'" />

    <div>
      <p>Other options:</p>
      <div class="flex space-x-2 items-center justify-center">
        <input
          v-model="formData.otherOptions.enableBottomInfo"
          id="enableBottomInfo"
          type="checkbox"
          class="w-4 h-4 accent-green-500 text-green-600 bg-gray-100 border-gray-300 rounded focus:ring-green-500 dark:focus:ring-green-600 dark:ring-offset-gray-800 focus:ring-2 dark:bg-gray-700 dark:border-gray-600"
        > 
        <label for="enableBottomInfo">Enable bottom info</label>

        <ColorPicker v-model="formData.otherOptions.backgroundColor" /> 
        <label for="backgroundColor" class="pl-4">Background color</label>

        <ColorPicker v-model="formData.otherOptions.borderBoxColor" /> 
        <label for="borderBoxColor" class="pl-4">BorderBox color</label>
      </div>
    </div>
    <div class="flex justify-center pt-2">
      <Button :type="'submit'" label="GENERATE !" />
    </div>
  </form>
</template>
