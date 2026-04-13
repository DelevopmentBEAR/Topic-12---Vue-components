<script setup>
import { ref } from 'vue';

defineProps({
  // These props will receive the question and answers from the parent component (App.vue)
  question: String,
  answer1: String,
  answer2: String
})

const choice = ref('') // This will store the user's choice

</script>

<template>
  <h2>Make your choice!</h2>

  <p>{{ question }}</p>
  <div class="radio-group">
    <!-- v-model binds the input to the choice ref -->
    <!-- v-bind connects the input to the corresponding answer prop -->
    <!-- id binds the label to the input -->
    <input v-model="choice" v-bind="answer1" type="radio" id="answer1">
    <label for="answer1">{{ answer1 }}</label>

    <input v-model="choice" v-bind="answer2" type="radio" id="answer2">
    <label for="answer2">{{ answer2 }}</label>
  </div>
</template>

<style scoped>
/* I wanted to keep the radio buttons inline */
.radio-group {
  display: inline; 
  gap: 10px; 
}
</style>
