<script setup>
import { ref, reactive } from 'vue'

const sarccCountries = reactive([
  { name: 'afghanistan', capital: 'kabul' },
  { name: 'bangladesh', capital: 'dhaka' },
  { name: 'bhutan', capital: 'thimphu' },
  { name: 'india', capital: 'new delhi' },
  { name: 'maldives', capital: 'male' },
  { name: 'nepal', capital: 'kathmandu' },
  { name: 'pakistan', capital: 'islamabad' },
  { name: 'sri lanka', capital: 'colombo' }
]);


const sarccCapitals = [
  'kabul',     // Afghanistan
  'dhaka',     // Bangladesh
  'thimphu',   // Bhutan
  'new delhi', // India
  'male',      // Maldives
  'kathmandu', // Nepal
  'islamabad', // Pakistan
  'colombo'    // Sri Lanka
];


function shuffleArray(arr) {
  const shuffledArr = arr.slice(); // Create a shallow copy of the original array
  for (let i = shuffledArr.length - 1; i > 0; i--) {
    const j = Math.floor(Math.random() * (i + 1));
    [shuffledArr[i], shuffledArr[j]] = [shuffledArr[j], shuffledArr[i]];
  }
  return shuffledArr;
}


function getScore() {
  let score = 0
  sarccCountries.forEach((country) => {
    if (country.capital == country.answer) {
      score++
    }
  });
  return score;
}


</script>

<template>
  <div class="container mx-auto w-full">
    <h2 class="text-4xl capitalize">Simple Quiz App</h2>
    <p class="mt-3">Score: {{ getScore() }}</p>
    <p class="mt-3">{{ sarccCountries }}</p>
    <!-- Input Box -->
    <div class=" mt-10 space-y-4">
      <!-- Single Question -->
      <div v-for="(country, index ) in sarccCountries" :key="country.name"
        class="text-left space-y-2  bg-gray-200 p-4 rounded-lg">
        <label class="text-xl capitalize block">{{ index + 1 }}. What is the name of capital city of {{ country.name
        }}</label>
        <!-- Options -->
        <div class="space-x-3">
          <template v-for="capitalName in sarccCapitals" :key="capitalName">
            <input type="radio" :name="country.name" v-model="country.answer" :value="capitalName">
            <label class=" capitalize ">{{ capitalName }}</label>
          </template>
        </div>
        <!-- Options End -->
      </div>
      <!-- Single Question End -->


    </div>
  </div>
</template>

<style scoped></style>