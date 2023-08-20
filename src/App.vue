<script setup>
import { ref } from 'vue';

const title = ref("TODO-APP")
const center = ref("center")
var task = ref('')
var id = 0

const todos = ref([
])

function addTask() {
  todos.value.push({ id: id++, text: task.value })
  task.value = ""
}

function remove(todo) {
  todos.value = todos.value.filter(item => item !== todo)
}


</script>

<template>
  <div :class="center">
    <h1>{{ title }} </h1>
    <input v-model="task" type="text">
    <button @click="addTask">Add</button>
  </div>

  <div>
    <ol>
      <li v-for="todo in todos" :key="todo.id">{{ todo.text }}<button @click="remove(todo)">Done</button></li>
    </ol>
  </div>
</template>


<style scoped>
.center {
  display: flex;
  flex-direction: column;
}
</style>
