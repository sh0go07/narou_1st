<script setup lang="ts">
import { ref } from 'vue'

interface ToDo {
    name: string
    isCompleted: boolean
}

const ToDos = ref<ToDo[]>([])
const newToDoName = ref('')

const addToDo = () => {
    if (!newToDoName.value) return
    ToDos.value.push({ name: newToDoName.value, isCompleted: false })
}


</script>

<template>
    <div>
        <div>やらなきゃ！</div>
        <ul>
            <li v-for="ToDo in ToDos.filter((v) => !v.isCompleted)" :key="ToDo.name">
               <div>{{ ToDo.name }}</div>
               <button @click=" ToDo.isCompleted = true">おわった！</button>
            </li>
        </ul>
        <div>おつかれさま！</div>
        <ul>
            <li v-for="ToDo in ToDos.filter((v) => v.isCompleted)" :key="ToDo.name">
               <div>{{ ToDo.name }}</div>
               <button @click=" ToDo.isCompleted = false">まだだった！</button>
            </li>
        </ul>
        <div>
            <label>
                やること！
                <input v-model="newToDoName" type="text" />
            </label>
            <button @click="addToDo">追加</button>
        </div>
    </div>
</template>

<style></style>