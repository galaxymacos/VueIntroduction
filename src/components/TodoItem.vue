
<script setup>
import {defineProps} from "vue";

defineProps({
      todo: Object
    })
</script>

<template>
  <li>{{ todo.text }}</li>
</template>