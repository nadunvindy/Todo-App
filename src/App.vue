<script setup>
import { ref } from 'vue';

const title = ref("TODOAPP")
const center = ref("center")
var task = ref('')
var id = 0

const todos = ref([
])

const done = ref([

])

function addTask() {
  todos.value.push({ id: id++, text: task.value })
  task.value = ""
}

function remove(todo) {
  todos.value = todos.value.filter(item => item !== todo)
  done.value.push(todo)
}


</script>

<template>
  <div class="flex flex-col text-center">
    <h1 class="text-3xl text-white">{{ title }} </h1>
    <div>
      <div class="flex align-middle justify-center">
        <input class="border-2 border-white w-40 bg-black text-white" v-model="task" type="text">
        <button class="text-black w-20 s bg-white rounded" @click="addTask">Add</button>
      </div>
    </div>

    <div class="flex h-96 w-full self-center justify-around">
    <div class="border-2 border-white w-60 h-5/6">
      <p class="text-white">TODO</p>
      <ol>
        <li class="text-white" v-for="todo in todos" :key="todo.id">{{ todo.text }}<button @click="remove(todo)"
            class="text-black border-2 border-black bg-white">Done</button></li>
      </ol>
    </div>
    <div class="border-2 border-white w-60 h-5/6">
      <p class="text-white">DONE</p>
      <ol>
        <li class="text-white" v-for="todo in done" :key="todo.id">{{ todo.text }}</li>
      </ol>
    </div>
  </div>

  </div>

 
</template>


<style scoped></style>
