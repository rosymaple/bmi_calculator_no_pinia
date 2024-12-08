<script setup>
import { ref } from 'vue'

const userHeight = ref('')
const userWeight = ref('')

const emit = defineEmits(['user-entered-data'])


// todo create a function here to run when the user clicks a button
// this function will emit a message to App.vue
// including the user's height and weight data
const userHasSubmittedData = () => {
  // this function will be called when the user clicks the calculate button
  // this component needs to tell App.vue that the data is available
  // and send App.vue this data so it can do the math
  emit ('user-entered-data', userHeight.value, userWeight.value) //todo include user weight
}

</script>

<template>

  <!-- HTML here, things the user sees -->
  <!-- can be updated from the script's state -->
  <!-- can tell the code the user has done something -->

  <h2>Enter your height and weight</h2>

  <label>Height in meters</label>
  <input v-model="userHeight">
  <br>

  <!-- todo use v-model -->
  <label>Weight in kilograms</label>
  <input v-model="userWeight">
  <br>

  <!-- todo use v-on to tell the script
  when the user clicks on the button -->
  <button v-on:click="userHasSubmittedData">Calculate!</button>

</template>

<style scoped>

</style>