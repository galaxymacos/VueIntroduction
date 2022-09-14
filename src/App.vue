<script setup>
import { ref } from 'vue'
import ChildComp from './components/ChildEmit.vue'

const childMsg = ref('No child msg yet')
</script>

<template>
<!--  listen for response event from child using v-on-->
  <ChildComp @response="(msg) => childMsg = msg" />
  <p>{{ childMsg }}</p>
</template>