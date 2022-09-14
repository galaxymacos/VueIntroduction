<script setup>
import {computed, ref} from 'vue'
const newTodo = ref('')
let id = 0
const todos = ref([
  { id: id++, text: 'Learn Vue 3', done: true },
  { id: id++, text: 'Learn Vue 3 Composition API', done: false },
  { id: id++, text: 'Build something awesome', done: false },
])
// Computed properties
const filteredTodos = computed(() => {
  if(hideDone.value) {
    return todos.value.filter(todo => !todo.done)
  }
  else{
    return todos.value
  }
})

const hideDone = ref(false)
function addTodo() {
  todos.value.push({
    id: id++,
    text: newTodo.value,
    done: false,
  })
}

function removeTodo(todo) {
  todos.value.splice(todos.value.indexOf(todo), 1)
}
</script>

<template>
  <form @submit.prevent="addTodo">
    <input v-model="newTodo">
    <button>Add Todo</button>
  </form>
  <ul>
    <li v-for="todo in filteredTodos" :key="todo.id">
<!-- Bind bool attribute to checkbox -->
      <input type="checkbox" v-model="todo.done">
      <span :class="{ done: todo.done }">{{ todo.text }}</span>
      <button @click="removeTodo(todo)">X</button>
    </li>
  </ul>
<!--inline function-->
  <button @click="hideDone = !hideDone">{{ hideDone ? 'Show Done' : 'Hide Done'}} </button>
</template>

<style>
.done {
  text-decoration: line-through;
}
</style>