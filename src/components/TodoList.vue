<script setup>
import TodoItem from './TodoItem.vue'

defineProps(['todos'])
</script>

<template>
  <div class="space-y-5">
    <TodoItem v-for="todo in todos" :key="todo.id" v-bind="todo" />
  </div>
</template>
