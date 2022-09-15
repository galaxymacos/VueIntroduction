<script setup>
import { ref } from 'vue'
const input = ref('Edit me')
const isChecked = ref(false)
const checkedName = ref(["Jack"])
const radio = ref('One')
const grade = ref('A')
const multipleSelect = ref(['A', 'B'])
</script>

<template>
  <h1>Text Input</h1>
    <!-- Input does not have to be in a form -->
    <!-- Input default type is text -->
    <input v-model="input"> {{ input }}

  <h2>Checkbox</h2>
  <!-- Checkbox -->
  <input type="checkbox" v-model="isChecked"> Checked: {{ isChecked }}

  <h2>Multi Checkbox</h2>
  <!-- Multi Checkbox will pass the "value" in each input to v-model -->
  <input type="checkbox" v-model="checkedName" id="jack" value="Jack">
  <label for="jack">Jack</label>
  <input type="checkbox" v-model="checkedName" id="john" value="John">
  <label for="john">John</label>
  <input type="checkbox" v-model="checkedName" id="mike" value="Mike">
  <label for="Mike">Mike</label>
  <p>Checked names:</p>
  <!-- Use <pre> for formatting in the mustache syntax -->
  <pre>{{ checkedName }}</pre>

  <h2>Radio</h2>
  <input type="radio" value="One" id="one" v-model="radio">
  <label for="one">One</label>
  <input type="radio" value="Two" id="two" v-model="radio">
  <label for="two">Two</label>
  <p>Picked: {{ radio }}</p>

  <h2>Select</h2>
  <select v-model="grade">
    <!--Add a placeholder in select-->
    <option disabled value="">Please select one</option>
    <option>A</option>
    <option>B</option>
    <option>C</option>
    <option>D</option>
  </select>
  <p>Selected: {{ grade }}</p>

  <h2>Multi Select</h2>
<!--  "multiple" attribute is required for multi select -->
  <select v-model="multipleSelect" multiple style="width: 300px">
    <option>A</option>
    <option>B</option>
    <option>C</option>
    <option>D</option>
  </select>
  <span>Selected: {{ multipleSelect }}</span>
</template>