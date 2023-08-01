<script setup>
import { ref, reactive } from 'vue'

const checkboxInput = ref(true)

</script>

<template>
  <div class="container mx-auto w-full">
    <h2 class="text-4xl capitalize mb-5">Random Image Showing Based On Checbox Input </h2>
    <p class="capitalize">{{ checkboxInput }}</p>
    <!-- Input Box -->
    <div class=" bg-gray-100 p-5 rounded-lg mt-5 min-h-screen">
      <div class=" bg-white p-5 rounded-md ">
        <label class="text-lg capitalize mr-3">Show image randomly:</label>
        <input type="checkbox" v-model="checkboxInput">
      </div>
      <div class="mt-5 text-left" v-show="checkboxInput == true">
        <img :src="`https://source.unsplash.com/random?version=${Math.random()}`" class="w-6/12 mx-auto rounded-md">
      </div>
    </div>


  </div>
</template>

<style scoped></style>