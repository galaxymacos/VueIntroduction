<script setup>
import { ref } from 'vue'
const message = ref("Hello world")

function reverseMessage() {
  message.value = message.value.split('').reverse().join('')
}

function notify() {
  alert(message.value)  // show alert with message
}

</script>
<template>
  <!--
    Note we don't need .value inside templates because
    refs are automatically "unwrapped" in templates.
  -->
  <h1>{{ message }}</h1>
  <button @click="reverseMessage">Reverse Message</button>
  <button @click="message = message+'!'">Add !</button>
  <a href="https://vuejs.org" @click.prevent="notify">A link</a> <!-- prevent default event (open link) -->
</template>

<style>
button, a {
  display: block; /* make them appear on separate lines */
  margin-bottom: 10px;
}
</style>