<script setup>
import { ref, reactive } from 'vue'

const colorsName = ref([])



</script>

<template>
  <div class="container mx-auto w-full">
    <h2 class="text-4xl capitalize">My fevorite colors</h2>
    <p class="mt-3">{{ colorsName }}</p>
    <!-- Input Box -->
    <div class="flex items-center mt-10 bg-gray-200 p-4 rounded-lg space-x-4">
      <div>
        <label class="text-xl capitalize mr-2">red:</label>
        <input type="checkbox" v-model="colorsName" value="red">
      </div>
      <div>
        <label class="text-xl capitalize mr-2">green:</label>
        <input type="checkbox" v-model="colorsName" value="green">
      </div>
      <div>
        <label class="text-xl capitalize mr-2">yellow:</label>
        <input type="checkbox" v-model="colorsName" value="yellow">
      </div>
      <div>
        <label class="text-xl capitalize mr-2">blue:</label>
        <input type="checkbox" v-model="colorsName" value="blue">
      </div>
    </div>
  </div>
</template>

<style scoped></style>