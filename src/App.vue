<script setup>
import { ref, reactive } from 'vue'

const colorName = ref('None')

function getStyle() {
  return ({
    backgroundColor: colorName.value
  })
}

</script>

<template>
  <div class="container mx-auto w-full">
    <h2 class="text-4xl capitalize">My fevorite color: {{ colorName }}</h2>
    <!-- Input Box -->
    <div class="flex items-center mt-10 bg-gray-200 p-4 rounded-lg space-x-2">
      <label class="text-xl" for="color">Input color:</label>
      <input type="text" v-model="colorName" id="color" class="p-1 px-2 rounded-md focus:outline-none">
    </div>
    <!--Color Output Div -->
    <div class=" w-36 h-36 mt-10 mx-auto rounded-lg ring-4 ring-gray-200" :style="getStyle()"></div>
  </div>
</template>

<style scoped></style>
