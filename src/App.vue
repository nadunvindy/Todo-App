<script setup>
import { ref } from 'vue';

const title = ref("TODO-APP")
const center = ref("center")
const task = ref('')
var id = ref(0)

const todos = ref([
])

function addTask(){
  todos.value.push({id:id++,text:task.value})
  task.value = ""
}


</script>

<template>
  <div :class="center">
    <h1>{{ title }} </h1>
    <p>{{ task }}</p>
    <input v-model="task" type="text" ref="todo">
    <button @click="addTask">Add</button>
  </div>

  <div>
    <ol>
      <li v-for="todo in todos" :key="todo.id">{{ todo.text }}</li>
    </ol>
  </div>
</template>


<style scoped>
.center {
  display: flex;
  flex-direction: column;
}
</style>
