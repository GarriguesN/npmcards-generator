<script setup>
  import Form from "@/components/Form.vue"
  import StarsBackground from "@/components/StarsBackground.vue"
  import Preview from "@/components/Preview.vue"
</script>

<template>
  <div id="content" class="flex-grow flex h-full">
    <div id="col1" class="flex flex-1 justify-center items-center">
      <StarsBackground/>
      <Form></Form>
  </div>


  <div id="col2" class="flex flex-col flex-1 border-l-2 w-full justify-center items-center align-middle border-green-700">
    <h1 class=" text-3xl font-mono ">NPX CARD PREVIEW</h1>
    <p class="mb-10 text-sm font-mono">This is a basic preview and may look different depending on your terminal</p>
    <Preview></Preview>
  </div>
  </div>
  
</template>
