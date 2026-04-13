<script setup>

import { ref, defineEmits, h } from 'vue'

const emit = defineEmits(['stats-entered'])

const height = ref(0)
const weight = ref(0)


function statsEntered() {
  // need to emit an event with the calculated BMI value
  // the event will be received by the parent component (App.vue) and displayed there
  // this component does not know and does not care about how the BMI value is displayed, it just emits the value to the parent component
  emit('stats-entered', height.value, weight.value)
}

</script> 

<template> 

<h2>Enter your Height and Weight</h2>

<label for="height">Height in meters:</label>
<input type="number" id="height" v-model="height" />

<label for="weight">Weight in kilograms:</label>
<input type="number" id="weight" v-model="weight" />

<button type="submit" v-on:click="statsEntered">Calculate BMI</button>

</template>

<style scoped> 

</style>