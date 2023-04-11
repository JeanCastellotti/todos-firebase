<script setup>
import { ref } from 'vue'

const emit = defineEmits(['create-todo'])

const todoLabel = ref('')

function createTodo() {
  emit('create-todo', todoLabel.value)
  todoLabel.value = ''
}
</script>

<template>
  <form @submit.prevent="createTodo" class="flex gap-2 mb-5">
    <input
      v-model="todoLabel"
      type="text"
      placeholder="Add a todo"
      class="border py-2 px-3 flex-1 rounded focus:outline-none focus:ring focus:ring-gray-200/75"
    />
    <button
      :disabled="!todoLabel"
      class="px-5 rounded bg-blue-500 text-white focus:outline-none focus:ring focus:ring-blue-500/50"
    >
      Add
    </button>
  </form>
</template>
