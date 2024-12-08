<script setup>
  import BodyMassIndexForm from './components/BodyMassIndexForm.vue'
  import { ref } from 'vue'

  // we need to declare a constant variable before...
  // the calculateBmi function
  const bmi = ref(0)

  // must add weight to bmi computation
  const calculateBMI = (height, weight) => {
    // todo do calculation with weight
    bmi.value = weight / (height * height)
    return bmi.value
    // return calculated bmi value to our program
  }

</script>

<template>
  <h1>Body Mass Index Calculator</h1>

  <!-- todo set this up to expect a message
  from BodyMassIndexForm and call a function here -->
  <!-- must listen for user-entered-data event...
  we must call the calculateBMI function if...
  userHasSubmittedData gets triggered by the calculate button -->
  <BodyMassIndexForm v-on:user-entered-data="calculateBMI" />
  <!-- displays BMI for the user -->
  <div>Your BMI is {{ bmi }}</div>
</template>

<style scoped>


</style>