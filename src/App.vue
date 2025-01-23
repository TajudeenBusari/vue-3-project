
<template>
  <!-- The mustache notation is used to render the value of the variable message and number
    -->
  <h1>message: {{ message }} </h1>
  <hr />
  <h1>number: {{ number }}</h1>
  <hr />
  <h1>doubleNumber(50): {{ doubleNumber(50) }}</h1>
  <hr />
  <h1>number * 2: {{ number * 2}}</h1>
  <hr />
  <h1> {{number > 150? 'number is greater than 150': 'number is less than 150' }}</h1>
  <hr />
  <h1 v-text="number"> </h1> <!-- v-text directive. Can be used instead of the mustache notation -->
  <hr />
  <h1>{{ harry }}</h1>
  <h1>{{ harry.name}}</h1>
  <hr />
  <h1>{{ tjwizards }}</h1>
  <h1>{{ tjwizards[0]}}</h1>
  <h1>{{ tjwizards[0].name}}</h1>
  <hr />
  <h1>{{ rawHtml }}</h1>
  <h1 v-text="rawHtml"></h1> <!--v-text renders as js code -->
  <h1 v-html="rawHtml"></h1> <!-- v-html directive. Can be used to render raw HTML -->
</template>

<script setup>
 let message = 'Hello, Vue!';
 let number = 50;
 function doubleNumber(num) {
   return num *= 2;
 }
 //JavaScript object and array
 //object
  const harry = {
    id: 1001,
    name: 'John Doe',
    house: 'Gryffindor',
    age: 30,
    wand: {
      core: 'phoenix feather',
      wood: 'holly',
      },
    };

    //array
  const tjwizards = [
      {
    id: 1001,
    name: 'Harry Potter',
    house: 'Gryffindor',
    age: 11,
    wand: {
      core: 'phoenix feather',
      wood: 'holly',
        },
      },

      {
    id: 1002,
    name: 'Hermione Granger',
    house: 'Phoenix feather',
    age: 17,
    wand: {
        core: 'phoenix feather',
        wood: 'vine',
        
            },
      },

        {
      id: 1003,
      name: 'Ron Weasley',
      house: 'Slytherin',
      age: 17,
      wand: {
        core: 'Dragon heartstring',
        wood: 'willow',
        
        },
      },

      {
      id: 1004,
      name: 'Draco Malfoy',
      house: 'Malfoy Manor',
      age: 15,
      wand: {
        core: 'Unicorn hair',
        wood: 'hawthorn',
        },
      }
      
    ];

    //rendering raw HTML
    const rawHtml = '<span style="color: red">This should be red</span>';

</script>

<style lang="scss" scoped>

</style>
