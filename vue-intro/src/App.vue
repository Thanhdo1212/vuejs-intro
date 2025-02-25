<script setup lang="ts">
import { ref } from 'vue'

// Biến theo dõi tên công việc và độ quan trọng
const inputTodo = ref('')
const isImportant = ref(false)

// Danh sách todos
const todos = ref([
  { id: 1, text: 'Do exercise', isImportant: true },
  { id: 2, text: 'Learn Vue.js', isImportant: false },
  { id: 3, text: 'Learn Nuxt.js', isImportant: true },
])

// Hàm thêm công việc
const addTodo = () => {
  if (inputTodo.value.trim() === '') return

  todos.value.push({
    id: todos.value.length + 1,
    text: inputTodo.value.trim(),
    isImportant: isImportant.value,
  })

  // Reset input
  inputTodo.value = ''
  isImportant.value = false
}
</script>

<template>
  <div>
    <h2>To-Do List</h2>

    <!-- Input nhập công việc -->
    <input type="text" placeholder="Type your to-do here" v-model="inputTodo" />

    <!-- Chọn mức độ quan trọng -->
    <label> <input type="radio" v-model="isImportant" :value="true" /> Important </label>
    <label> <input type="radio" v-model="isImportant" :value="false" /> Not Important </label>

    <!-- Nút thêm công việc -->
    <button @click="addTodo">Add Todo</button>

    <!-- Danh sách công việc -->
    <ul>
      <li
        v-for="todo in todos"
        :key="todo.id"
        :style="{ color: todo.isImportant ? 'red' : 'black' }"
      >
        {{ todo.text }}
      </li>
    </ul>
  </div>
</template>
