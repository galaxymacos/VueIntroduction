<script setup>
import { ref, onMounted } from 'vue'

const p = ref(null) // p must match the ref name in the template
onMounted(() => {
  p.value.textContent = 'Hello World'
})
</script>

<template>
<!--  ref = a reference to an element in the template to be used in the script setup-->
  <p ref="p"></p>
</template>