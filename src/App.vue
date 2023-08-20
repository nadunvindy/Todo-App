<script setup>
import { ref } from 'vue';

const title = ref("TODO-APP")
const center = ref("center")
const task = ref('')
var id = ref(0)
var newtask = ref('')

const todos = ref([])
</script>

<template>
  <div :class="center">
    <h1>{{ title }} </h1>
    <p>{{ task }}</p>
    <input v-model="task" type="text" ref="todo">
    <button>Add</button>
  </div>
</template>


<style scoped>
.center {
  display: flex;
  flex-direction: column;
}
</style>
