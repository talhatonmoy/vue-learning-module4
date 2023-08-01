<script setup>
import { ref, reactive } from 'vue'

const person = reactive({
  name: 'Jon Deo',
  age: '25',
  title: 'CEO',
  company: 'Marvel Cenematic Universe'
});

</script>

<template>
  <div class="container mx-auto w-full">
    <h2 class="text-4xl capitalize mb-5">Person Detail</h2>
    <p>{{ person }}</p>
    <!-- Input Box -->
    <div class=" bg-gray-200 p-5 rounded-lg mt-5">
      <div v-for="(value, key, index) in person" :key="index" class="mt-5 text-left">
        <label class="text-lg block mb-1 capitalize" for="color">{{ key }}:</label>
        <input type="text" v-model="person[key]" id="color" class="p-1 px-2 w-full rounded-md focus:outline-none">
      </div>
    </div>
  </div>
</template>

<style scoped></style>
