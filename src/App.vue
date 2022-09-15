<script setup>
import { ref } from 'vue'
const numbers = ref([1, 2, 3])
const visible = ref(true)
</script>

<template>
  <button @click="visible = !visible">Toggle List</button>
  <button @click="numbers.push(numbers.length + 1)">Push Number</button>
  <button @click="numbers.pop()">Pop Number</button>
  <button @click="numbers.reverse()">Reverse List</button>
  <ul v-if="visible && numbers.length">
    <li v-for="number in numbers" :key="numbers.indexOf(number)">
      {{ number }}
    </li>
  </ul>
  <p v-else-if="numbers.length">List is hidden, but it is not empty</p>
  <p v-else>List is empty</p>
</template>