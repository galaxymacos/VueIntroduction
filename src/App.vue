

<script setup>
import {ref, watch} from 'vue'
const id = ref(1)
const todoData = ref(null)
async function fetchData() {  // async function
  todoData.value = null
  const res = await fetch(`https://jsonplaceholder.typicode.com/todos/${id.value}`) // wait for fetch
  todoData.value = await res.json() // await all functions in the chain (source is not immediately available)
}
fetchData()
watch(id, fetchData)  // watch id and call fetchData when id changes
</script>

<template>
  <p>Todo id: {{ id }}</p>
  <button @click="id++">Fetch new data</button>
<!--  show loading when todoData is null (set in script setup)-->
  <p v-if="!todoData">Loading</p>
  <pre v-else>{{ todoData }}</pre>
</template>