<!--Vue composition API-->

<script setup>
import {ref} from "vue";
const count = ref(0);
function onClick() {
  count.value++;
}
</script>

<template>
  <button @click="onClick">Count is {{count}}</button>
</template>
