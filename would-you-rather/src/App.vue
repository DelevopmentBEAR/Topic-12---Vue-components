<script setup>
import WouldYouRather from './components/WouldYouRather.vue'
import {ref} from 'vue'

// These will hold the question and answers for the "Would You Rather" game
const wyrQuestion = ref('Would you rather be invisible or be able to fly?')
const wyrAnswer1 = ref('Be invisible')
const wyrAnswer2 = ref('Be able to fly')

// This will store the user's choice
const userChoice = ref('')

function updateUserSelection(choice) {
  // This function will be called when the user makes a choice in the WouldYouRather component
  userChoice.value = `Thanks! You chose: ${choice}` // Update the userChoice ref with the selected answer
  console.log('User selected:', userChoice.value) // Log the user's choice to the console for now
}

</script>

<template>
  <div id="app-component">
  <h1>Would You Rather?</h1>

  <!-- Passes the question and answers as props to the WouldYouRather component -->
  <WouldYouRather 
  v-bind:question="wyrQuestion" 
  v-bind:answer1="wyrAnswer1" 
  v-bind:answer2="wyrAnswer2"
  v-on:answer-chosen="updateUserSelection" /> 
  <!-- Listens for the 'answerChosen' event from the WouldYouRather component and call updateUserSelection when it occurs -->
  <b><p v-if="userChoice"> {{ userChoice }}</p></b> <!-- Display the user's choice -->
  </div>
</template>

<style scoped>
/* Styles will be applied to both the app component and its children */
#app-component {
  text-align: center;
  font-family: 'Arial', sans-serif;
}

 p {
  font-family: 'Courier New', Courier, monospace;
}
</style>