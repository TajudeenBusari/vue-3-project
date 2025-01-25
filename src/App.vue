<!-- v.model -->

<template>
  <h1>{{message}}</h1>
  <h1>Welcome, {{ formData.name }}</h1>
  <form action="">
    <div>
      <span>Name:</span>
      <span>
          <input type="text" v-model.lazy="formData.name"/>
      </span>
    </div>
    <div>
      <span>Gender:</span>
      <span>
        <input type="radio" id="male" value="M" v-model="formData.gender"/>
        <label for="male">M</label>
        <input type="radio" id="female" value="F" v-model="formData.gender"/>
        <label for="female">F</label>
      </span>
    </div>
    <div>
      <span>Age:</span>
      <span>
        <input type="text" id="age" v-model.number="formData.age"/>
      </span>
    </div>
    <div>
      <span>Hobbies:</span>
      <input type="checkbox" value="Reading" v-model="formData.hobbies"/>
      <label for="Reading">Reading</label>
      <input type="checkbox" value="football" v-model="formData.hobbies"/>
      <label for="football">Football</label>
      <input type="checkbox" value="java" v-model="formData.hobbies"/>
      <label for="java">Java</label>
    </div>
    <div>
      <span>Profession:</span>
      <span>
        <select v-model="formData.profession">
          <option value="">Please select one</option>
          <option value="1">Software developer</option>
          <option value="2">Data Scientist</option>
          <option value="3">Professor</option>
          <option value="4">Chemist</option>
        </select>
      </span>
    </div>
    <div>
      <span>Description:</span>
        <textarea v-model.trim="formData.desc" @keydown.enter="submitForm"></textarea>
    </div>
    <div>
      <input type="reset" @click="resetForm" />
      <!-- prevent thw form from sumitting through form action -->
      <input type="submit"  @click="submitForm" />
    </div>
  </form>
</template>

<script setup>
import { ref } from 'vue'
let message = ref('Hello, v-model!')

let formData = ref({
  name: '',
  gender: '',
  age: '',
  hobbies: [],
  profession: '',
  desc: ''
})

// reset form
function resetForm(){
  //assign empty values to the form data
  formData.value = {
    name: '',
    gender: '',
    age: '',
    hobbies: [],
    profession: '',
    desc: ''
  }
}

 //submit form
 function submitForm(){
    console.log(JSON.stringify(formData.value))
  }
</script>

<style scoped>

</style>