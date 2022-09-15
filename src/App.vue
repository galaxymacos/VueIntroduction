<script setup>
import { ref } from 'vue'
const numbers = ref([])
const visible = ref(true)
function addNumber() {
  numbers.value.push(numbers.value.length + 1)
}
function removeNumber() {
  numbers.value.pop()
}
numbers.value.push(1)
numbers.value.push(2)
numbers.value.push(3)

function reverse() {
  numbers.value.reverse()
}

function toggleList() {
  visible.value = !visible.value
}

</script>

<template>
  <button @click="toggleList">Toggle List</button>
  <button @click="addNumber">Push Number</button>
  <button @click="removeNumber">Pop Number</button>
  <button @click="reverse">Reverse List</button>
  <ul v-if="visible">
    <li v-for="number in numbers" :key="numbers.indexOf(number)">
      {{ number }}
    </li>
  </ul>
  <p v-else>List is hidden</p>
</template>