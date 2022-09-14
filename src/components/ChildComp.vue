<script setup>
import { defineProps } from 'vue'
defineProps({ // A child component can accept input from the parent component using props.
  msg: String
})
</script>

<template>
  <h2>{{ msg || 'No props passed yet' }}</h2>
</template>