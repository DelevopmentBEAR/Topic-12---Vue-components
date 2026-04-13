<script setup>
import WouldYouRather from './components/WouldYouRather.vue'
import {ref} from 'vue'

// These will hold the question and answers for the "Would You Rather" game
const wyrQuestion = ref('Would you rather be invisible or be able to fly?')
const wyrAnswer1 = ref('Be invisible')
const wyrAnswer2 = ref('Be able to fly')

// This will store the user's choice
const userChoice = ref('')

</script>

<template>
  <h1>Would You Rather?</h1>

  <!-- Passes the question and answers as props to the WouldYouRather component -->
  <WouldYouRather 
  v-bind:question="wyrQuestion" 
  v-bind:answer1="wyrAnswer1" 
  v-bind:answer2="wyrAnswer2" />
</template>
