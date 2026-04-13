<script setup>
import BodyMassIndexForm from './components/BodyMassIndexForm.vue'

import { ref } from 'vue'

const bmi = ref() // value is undefined which is "Falsey"

function calculateBmi(height, weight) {
  // BMI formula: weight (kg) / (height (m) * height (m))
  // alert('Calculating BMI...' + ' ' + height + ' ' + weight)
   bmi.value = weight / (height * height)
}

</script>

<template>
  <h1>Body Mass Index Calculator</h1>

  <BodyMassIndexForm v-on:stats-entered="calculateBmi" />

<h3>Results</h3>
  <p v-if="bmi">Your BMI is: {{ bmi.toFixed(2) }}</p>
  <p v-else>Please enter data into the form.</p>

  <!-- App.vues knows about BodyMassIndexForm -->
  <!-- BodyMassIndexForm does NOT know about App.vue -->
  <!-- That's by design, so we can re-use components -->
</template>
