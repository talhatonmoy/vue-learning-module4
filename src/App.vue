<script setup>
import { ref, reactive } from 'vue'

const persons = reactive([
  {
    name: 'John Doe',
    age: 30,
    email: 'john.doe@example.com',
    phone: '555-1234',
    address: '123 Main Street, Cityville'
  },
  {
    name: 'Jane Smith',
    age: 25,
    email: 'jane.smith@example.com',
    phone: '555-5678',
    address: '456 Park Avenue, Townsville'
  },
  {
    name: 'Michael Johnson',
    age: 28,
    email: 'michael.johnson@example.com',
    phone: '555-9876',
    address: '789 Elm Road, Villagetown'
  },
  {
    name: 'Emily Williams',
    age: 22,
    email: 'emily.williams@example.com',
    phone: '555-4321',
    address: '321 Oak Lane, Countryside'
  },
  {
    name: 'Daniel Brown',
    age: 35,
    email: 'daniel.brown@example.com',
    phone: '555-8765',
    address: '567 Pine Street, Hamletville'
  },
  {
    name: 'Sophia Davis',
    age: 29,
    email: 'sophia.davis@example.com',
    phone: '555-2345',
    address: '432 Birch Avenue, Riverside'
  },
  {
    name: 'William Miller',
    age: 31,
    email: 'william.miller@example.com',
    phone: '555-7654',
    address: '678 Maple Court, Suburbia'
  },
  {
    name: 'Olivia Wilson',
    age: 27,
    email: 'olivia.wilson@example.com',
    phone: '555-3456',
    address: '876 Cherry Lane, Urbanville'
  },
  {
    name: 'James Anderson',
    age: 33,
    email: 'james.anderson@example.com',
    phone: '555-6543',
    address: '345 Walnut Drive, Metropolis'
  },
  {
    name: 'Emma Taylor',
    age: 26,
    email: 'emma.taylor@example.com',
    phone: '555-8765',
    address: '543 Cedar Street, Citytown'
  }
]);

const activeIndex = ref(0);



</script>

<template>
  <div class="container mx-auto w-full block min-h-screen">
    <h2 class="text-4xl capitalize">Live Data Editing - {{ activeIndex }}</h2>
    <p class="mt-3">{{ persons }}</p>
    <!-- Input Box -->
    <div class=" mt-10 space-y-4">
      <div class="flex items-start mt-10 space-x-3">
        <!-- Select Person -->
        <div class=" space-y-2 bg-gray-200 p-4 rounded-lg w-4/12">
          <label class="text-xl mr-3" for="sp">Select Person:</label>
          <select v-model="activeIndex" class="p-1 min-w-[150px] px-2 rounded-md focus:outline-none" id="sp">
            <option v-for="(person, index) in persons" :key="index" :value="index">{{ person.name }}</option>
          </select>
        </div>
        <!-- Select Person End-->

        <!-- Person Data -->
        <div class=" bg-gray-200 p-5 rounded-lg w-8/12">
          <!-- Single Input Field -->
          <div v-for="(value, key, index) in persons[activeIndex]" :key="key" class="mb-3 text-left">
            <label class="text-lg block mb-1 capitalize" for="color">{{ key }}:</label>
            <input type="text" v-model="persons[activeIndex][key]" id="color"
              class="p-1 px-2 w-full rounded-md focus:outline-none">
          </div>
          <!-- Single Input Field End-->
        </div>
        <!-- Person Data End -->
      </div>


    </div>
  </div>
</template>

<style scoped></style>