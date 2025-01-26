
<template>
  <h1>{{ message }}</h1>
  <p>
    what has keys but can't open locks space but no room and 
    can't go outside? what am i?
  </p>
  <button style="width: 200px;" @click="showAnswer = !showAnswer">{{ !showAnswer? 'Show me the answer!' : 'Hide the answer!'}}</button>
  <!-- Add the answer here but I dont to show the answer by default on the UI
   so, let define a method in the script-->
   <!-- v-show VS v-if
     v-show is simpler and the element is always rendered
     in the DOM tree regardless of initial condition with the
     css based toggling.

     v-if has higer toggle cost bcos it creates and destroys 
     elememt but it is more efficient.
   -->
  <div v-if="showAnswer">A keybaord via v-if.</div>

  <div v-show="showAnswer">A keybaord via v-show.</div>


  <!--<div v-if="Math.random()>0.5"> You are lucky!</div>
  <div v-else> You are not lucky!</div>-->

</template>

<script setup>
import { ref } from 'vue'

let message = ref('Riddle me this!')

let showAnswer = ref(false)
</script>

<style scoped>

</style>