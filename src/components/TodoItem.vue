<script setup>
import { inject } from 'vue'

defineProps(['id', 'label', 'done'])

const removeTodo = inject('removeTodo')
const toggleDone = inject('toggleDone')
</script>

<template>
  <div
    class="bg-white shadow rounded p-5 flex items-center"
    :class="done ? 'bg-green-50' : 'bg-white'"
  >
    <span class="mr-auto" :class="done && 'text-green-400 line-through'">{{ label }}</span>
    <div class="space-x-2">
      <button
        @click="toggleDone(id)"
        class="py-1 px-3 rounded"
        :class="done ? 'bg-green-400 text-white' : 'bg-slate-200'"
      >
        &check;
      </button>
      <button @click="removeTodo(id)" class="py-1 px-3 rounded bg-red-500 text-white">
        &cross;
      </button>
    </div>
  </div>
</template>
