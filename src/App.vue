<!--Vue composition API-->

<script setup>
import { ref, reactive } from 'vue'

const counter = reactive({ count: 0})  // reactive contains an object
const message = ref("Count is:")  // ref contains a value
</script>

<template>
  <h1>{{ message }}</h1>
  <p>{{ counter.count }}</p>
</template>