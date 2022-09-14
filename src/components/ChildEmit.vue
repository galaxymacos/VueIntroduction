<script setup>
import { defineEmits } from 'vue'
const emit = defineEmits(['response'])
// defineEmits() returns a function that emits events and defines a list of events that can be emitted
emit('response', 'Hello from ChildComp')  // emit an event to parent
</script>

<template>
  <p>Child Component</p>
</template>