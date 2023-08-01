<script setup>
import { ref, reactive } from 'vue'

const radioInput = ref(true)

</script>

<template>
  <div class="container mx-auto w-full">
    <h2 class="text-4xl capitalize mb-5">Random Image Showing Based On Radio Input </h2>
    <p class="capitalize">{{ radioInput }}</p>
    <!-- Input Box -->
    <div class=" bg-gray-100 p-5 rounded-lg mt-5 min-h-screen">

      <div class=" bg-white p-5 rounded-md ">
          <label class="text-lg capitalize mb-1">Show image randomly: Radio Input</label>
          <p>
            <input type="radio" name="displayimg" :value="true" v-model="radioInput"> On <br>
            <input type="radio" name="displayimg" :value="false" v-model="radioInput"> Off <br>
          </p>
        </div>

      <div class="mt-5 text-left" v-show="radioInput == true">
        <img :src="`https://source.unsplash.com/random?version=${Math.random()}`" class="w-6/12 mx-auto rounded-md">
      </div>
    </div>


  </div>
</template>

<style scoped></style>
