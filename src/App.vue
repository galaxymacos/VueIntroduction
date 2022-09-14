<script setup>
import { ref } from 'vue'
import ChildComp from './components/ChildComp.vue'  // Import the child component

const greeting = ref('Hello from parent')
</script>

<template>
<!--  Pass the greeting variable to the child component, the name "msg" must be declared in the defineProps in child -->
  <ChildComp :msg="greeting" />
</template>