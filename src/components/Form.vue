<script setup>
import { ref } from 'vue';
import Input from "@/components/Input.vue"
import Button from "@/components/Button.vue"

const handleSubmit = (event) => {
  event.preventDefault();
  // Form logic
  console.log('Send it!');
};
</script>


<template>
  <form class="w-[70%] space-y-5" @submit="handleSubmit">
    <div class="flex justify-between">
      <Input ids="nameInput" idCheckbox="nameCheckbox" label="Your name!" info="name" placeholder="Your name" />
      <Input ids="usernameInput" idCheckbox="usernameCheckbox" label="Your username!" info="@" placeholder="Your username" />
    </div>
    <Input ids="npmInput" idCheckbox="npmCheckbox" label="Your npm username!" info="https://npmjs.com/~" placeholder="npmuser" />
    <Input ids="githubInput" idCheckbox="githubCheckbox" label="Your github tag!" info="https://github.com/" placeholder="githubtag" />
    <Input ids="linkedinInput" idCheckbox="linkedinCheckbox" label="Your LinkedIn Url Tag!" info="https://www.linkedin.com/in/" placeholder="linkedinurl" />
    <Input ids="wakatimeInput" idCheckbox="wakatimeCheckbox" label="Your wakatime user!" info="https://wakatime.com/" placeholder="wakatimename" />
    <Input ids="cardInput" idCheckbox="cardCheckbox" label="Your package name (check it's available!)" info="npx" placeholder="Name of the package" />

    <div class="flex justify-center pt-2">
      <Button :type="'submit'" label="GENERATE !" />
    </div>
    

  </form>
</template>



<style></style>