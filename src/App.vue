<script setup>
import { ref } from 'vue'
let todo_id = 0

const new_todo = ref('')

const todos = ref([
  { id: 3, text: 'Learn Vue 3' },
  { id: 2, text: 'Learn Vue 3 Composition API' },
  { id: 1, text: 'Learn Vue 3 Composition API with TypeScript' },
])

function saveTodo() {
  todos.value.push({ id: todo_id++, text: new_todo.value }) // use push to add list element at the end
  new_todo.value = ''
}

function removeTodo(todo) {
  todos.value.splice(todos.value.indexOf(todo), 1)  // use splice to remove list element
}

</script>

<template>
  <form @submit.prevent="saveTodo">
    <input v-model="new_todo">
    <button>Add todo</button>
  </form>
  <ul>
<!--  key is used to bind a <li> with key. <li> will fully refresh if key is changed.-->
    <li v-for="todo in todos" :key="todo.id">
      {{todo.text}}
      <button @click="removeTodo(todo)">X</button>
    </li>
  </ul>
</template>