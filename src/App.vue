<template>
  <h1>{{ message }}</h1>
  <!-- both buttons are same i.e  v-on:click = @click -->
  <button v-on:click="replaceText('v-on is fun1')">Replace text</button>
  <button @click="replaceText('v-on is fun2')">Replace text</button>

  <hr />
  <!-- we are listening to a keydown event -->
   <p>An input field where the user can ONLY enter numbers:</p>
  <input type="text" @keydown="handleInput($event)" />

  <hr />
  <!-- we are prventing the default context menu when the style is right clicked and 
   implementing a custom context menu. We have disabled the original context menu 
   Use case is if email is not correct, password is not strong enough, can be used to 
   implement custom drag and drop etc. This is called event modifier in vue.js-->
  <div style="width: 100px; height: 100px; background-color: red;" 
  @contextmenu.prevent="console.log('Show a custom context menu')">
  </div>

  <hr />
  <!-- .stop event -->
  <div id="mouseover" @mouseover="fun1">
    <textarea @mouseover.stop="fun2($event)">This is a text area.</textarea>
  </div>

  <hr />
  <!-- key down .enter-->
  <div>
    press down "Enter" key to trigger a console log print:
    <input type="text" @keydown.enter="console.log('Enter key pressed')">
  </div>
  <!-- Arrow down key-->
  <div>
    press down "Arrow" key to trigger a console log print:
    <input type="text" @keydown.down="console.log('Arrow down key pressed')">
  </div>
  <!-- Arrow up key-->
  <div>
    press down "Up" key to trigger a console log print:
    <input type="text" @keydown.up="console.log('Arrow up key pressed')">
  </div>
  <!-- Arrow left key-->
  <div>
    press down "Left" key to trigger a console log print:
    <input type="text" @keydown.left="console.log('Arrow left key pressed')">
  </div>
  <!-- Arrow space key-->
  <div>
    press down "Space" key to trigger a console log print:
    <input type="text" @keydown.space="console.log('Space key pressed')">
  </div>
  <!-- b key-->
  <div>
    press down "b" key to trigger a console log print:
    <input type="text" @keydown.b="console.log('b key pressed')">
  </div>
  <!-- control c key-->
  <div>
    press down "Control" + "c" key to trigger a console log print:
    <input type="text" @keydown.ctrl.c="console.log('Control + c key pressed')">
  </div>

</template>

<script setup>
import { ref } from 'vue'

let message = ref('Hello, Vue 3!')

//define method to replace text
function replaceText(msg) {
  message.value = msg
}

//define method to handle input
function handleInput(event) {
  console.log(event)
  //if the key pressed is not a number, prevent the default action
  let keyCode = event.keyCode
  if(keyCode < 48 || keyCode > 57){
    //key code 48 to 57 are numbers from 0 to 9
    event.preventDefault() 
  }

}

//define method to handle mouseover event
function fun1() {
  console.log('Mouseover event on div')
}

function fun2(event) {
  //event.stopPropagation()
  console.log('Mouseover over textarea')
}

</script>

<style scoped>
#mouseover {
  margin: 1000px;
  text-align: right;
  background-color: purple;
  width: 300px;
  height: 300px;
  
}
</style>