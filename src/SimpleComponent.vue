<script setup>
import { ref } from 'vue'
import TodoItem from './components/TodoItem.vue'
const groceryList = ref([
  {id: 1, text: "vegetables"},
  {id: 2, text: "milk"},
  {id: 3, text: "whatever"},
])
</script>

<template>
  <ol>
    <TodoItem v-for="item in groceryList" :todo="item" :key="item.id"></TodoItem>
  </ol>
</template>
