<template>
  <div class="card">
    <h2>Message:{{ message }}</h2>
    <h2>Number:{{ number }}</h2>
    <button @click="changeMessageToUpperCase">Change message to upper case</button>
    <button @click="increamentNumber">Increment number</button>
  </div>
  <div class="card">
    <h2>Name: {{ wizard.name }}</h2>
    <h2>Wand: {{ wizard.wand }}</h2>
    <button @click="changeNameToUpperCase">Change name to upper case</button>
    <button @click="changeWandCore">Change wand core</button>
    <button @click="changeWizard">Change wizard</button>
  </div>
  <div class="card">
    <h2>Array: {{ wizards }}</h2>
    <button @click="wizards.push('Albus Dumbledore')">Add new wizard</button>

  </div>
    
</template>

<script setup>
import { ref } from 'vue';

let message = ref('Hello Reactivity!');
let number = ref(1);
function changeMessageToUpperCase() {
  //remmeber to use .value to access the value of ref
  message.value = message.value.toUpperCase();
  
  console.log(message);
}
function increamentNumber() {
  //remmeber to use .value to access the value of ref
  number.value += 1;
  console.log(number);
  }

  //javascript object
  let wizard = ref({
    id: 1001,
    age: 25,
    name: 'Harry Potter',
    house: 'Gryffindor',
    wand: {
      core: 'phoenix feather',
      wood: 'holly'
    }
  });

  //define the three methods
  function changeNameToUpperCase() {
    wizard.value.name = wizard.value.name.toUpperCase();
  }

  function changeWandCore() {
    wizard.value.wand.core = 'dragon heartstring';
  }

  function changeWizard() {
    wizard.value = {
      id: 1002,
      age: 25,
      name: 'Hermione Granger',
      house: 'Gryffindor',
      wand: {
        core: 'dragon heartstring',
        wood: 'vine'
      }
    }
  }

  //ref array
  let wizards = ref([
    'Harry Potter', 'Hermione Granger', 'Ron Weasley'
  ]);

</script>

<style lang="scss" scoped>

</style>