<script setup>
import { ref } from 'vue';

const title = ref("TODO-APP")
const center = ref("center")
</script>

<template>
  <div :class="center">
    <h1>{{ title }} </h1>
    <input type="text" ref="todo">
    <button>Add</button>
  </div>
</template>


<style scoped>
.center{
  display: flex;
  flex-direction: column;
}

</style>
