<script setup>
import { provide, ref } from 'vue'
import TodoList from './components/TodoList.vue'
import TodoAdd from './components/TodoAdd.vue'

const todos = ref([])

function addTodo(todoLabel) {
  todos.value.unshift({
    id: Symbol(),
    label: todoLabel,
    done: false
  })
}

function removeTodo(id) {
  todos.value = todos.value.filter((todo) => todo.id !== id)
}

function toggleDone(id) {
  const todo = todos.value.find((todo) => todo.id === id)
  todo.done = !todo.done
}

provide('removeTodo', removeTodo)
provide('toggleDone', toggleDone)
</script>

<template>
  <div class="min-h-screen bg-gray-100">
    <div class="max-w-md mx-auto p-5">
      <h1 class="text-center text-2xl font-semibold mb-5">Todos App</h1>
      <TodoAdd @create-todo="addTodo" />
      <TodoList :todos="todos" />
    </div>
  </div>
</template>
