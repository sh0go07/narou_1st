<script setup lang="ts">
import ToDoList from './ToDoList.vue'

defineProps<{
  msg: string
}>()
</script>

<template>
  <div>
    <h1>{{ msg }}</h1>
    <ToDoList />
  </div>
</template>

<style scoped>
a {
  color: #42b983;
}
</style>
