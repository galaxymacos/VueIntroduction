<script setup>
import JSConfetti from 'js-confetti'

const confetti = new JSConfetti()

function showConfetti() {
  confetti.addConfetti()
}

showConfetti()
</script>

<template>
  <h1 @click="showConfetti">Congratulations</h1>
</template>

<style>
 h1 {
   font-size: 3rem;
   text-align: center;
   margin-top: 10rem;
   cursor: pointer;
 }
</style>