
<template>
  <h1>{{ message }}</h1>
  <img v-bind:src="imageUrl" alt="" />

  <br />
  <img :src="imageUrl" alt="" />

  
  <button @click="changeImage">Change Image</button>

  <hr />
  <input type="text" :value="defaultInputText" />

  <hr>
  <p :class="className">Harry Potter</p>

  <p :class="{inactive: isInactive, center: isCenter}">Harry Potter</p>

  <p :class="['active', 'center']">Harry Potter</p>


</template>

<script setup>
import { ref } from 'vue'

// Reactive variables
let message = 'Hello v-bind'
let imageUrl = ref(new URL('@/assets/banner_1.jpeg', import.meta.url).href)

//Method to change the image
function changeImage(){
  imageUrl.value = new URL('@/assets/banner_2.jpeg', import.meta.url).href
}

let defaultInputText = 'Write something here...'

let className = 'active'

let isInactive = ref(false)
let isCenter = ref(false)
  
</script>

<style  scoped>
img{
 max-width: 300px;
}
.active{
  color: green;
}
.inactive{
  color: red;
  text-decoration: line-through;
}
.center{
  text-align: center;
} 

</style>