<script setup>
const numbers = [1, 3, 6, 78, 0];

const todos = [
  { id: 1, task: "Taking vuejs class", status: "In Progress" },
  { id: 2, task: "Upload source code", status: "Done" },
  { id: 3, task: "Check quiz questions", status: "Done" },
  { id: 4, task: "Ready quiz questions", status: "In Progress" },
];

// const persons = {
//   name: "John Doe",
//   age: 20,
//   gender: "Male",
//   profession: "Vuejs Developer",
// };

// const persons = [
//   {
//     name: "John Doe",
//     age: 20,
//     gender: "Male",
//     profession: "Vuejs Developer",
//   },
//   {
//     name: "Abina",
//     age: 40,
//     gender: "Female",
//     profession: "Vuejs Developer",
//   },
// ];
</script>

<template>
  <!-- <p v-for="(number, index) in numbers" :key="index">{{ index +": "+ number }}</p> -->
  <!-- <p v-for="(number, index) in 2" :key="index">{{ index + ": " + number }}</p> -->
  <!-- <p v-for="(number, index) in 3" :key="index">{{ index + ": " + numbers[number-1] }}</p> -->

  <h1>In Progress</h1>
  <!-- <ul>
    <template v-for="todo in todos" :key="todo.id">
      <li v-if="'In Progress' == todo.status">{{ todo.task }}</li>

      <li>{{ todo.task }}</li>
      <li>{{ todo.status }}</li>
    </template>
  </ul> -->

  <ul>
    <template v-for="todo in todos" :key="todo.id">
      <!-- <li class="list" :class="('Done' == todo.status)? 'line': ''">{{ todo.task }}</li> -->
      <li class="list" :class="{ line: 'Done' == todo.status }">
        {{ todo.task }}
      </li>
    </template>
  </ul>

  <!-- <h1>Person</h1>
  <p v-for="(person, key, index) in persons" :key="index">
    {{ key + ": " + person }}
  </p> -->

  <h1>Person</h1>
  <div v-for="(person, index) in persons" :key="index">
    <p v-for="(v, k, i) in person" :key="i">{{ k + ": " + v }}</p>
  </div>

  <!-- <h1>Pending</h1>
  <ul>
    <li v-for="todo in todos" :key="todo.id" v-show="'Pending' == todo.status">
      {{ todo.task }}
    </li>
  </ul>
  <h1>Done</h1>
  <ul>
    <li v-for="todo in todos" :key="todo.id" v-show="'Done' == todo.status">
      {{ todo.task }}
    </li>
  </ul> -->
</template>

<style scoped>
.line {
  text-decoration: line-through;
}
</style>