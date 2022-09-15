<script setup>
import { ref } from 'vue'
const hiddenText = ref("hidden text")
const isRed = ref(false)
const color = ref("green")

function changeColor() {
  if (color.value === "green") {
    color.value = "red"
  } else {
    color.value = "green"
  }
}
</script>
<template>
<!-- directly change the value of an attribute-->
  <p :title="hiddenText">Hover</p>
<!--  use bool to add toggle a value on and off in the attribute -->
  <p :class="{red: isRed}" @click="isRed = !isRed">Red or nothing</p>
<!--  use string to toggle an attribute in style -->
  <p :style="{color: color}" @click="changeColor">Red or green</p>

</template>
<style>
 .red {
   color: red;
 }
</style>