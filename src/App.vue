<template>
  <div class="min-h-screen bg-gray-100">
    <div class="max-w-md mx-auto p-5">
      <h1 class="text-center text-2xl font-semibold mb-5">Todos App</h1>

      <form @submit.prevent class="flex gap-2 mb-5">
        <input
          type="text"
          placeholder="Add a todo"
          class="border py-2 px-3 flex-1 rounded focus:outline-none focus:ring focus:ring-gray-200/75"
        />
        <button
          class="px-5 rounded bg-blue-500 text-white focus:outline-none focus:ring focus:ring-blue-500/50"
        >
          Add
        </button>
      </form>

      <div class="space-y-5">
        <div v-for="i in 3" class="bg-white shadow rounded p-5 flex items-center">
          <span class="mr-auto">Lorem ipsum dolor sit amet.</span>
          <div class="space-x-2">
            <button class="py-1 px-3 rounded bg-slate-100">&check;</button>
            <button class="py-1 px-3 rounded bg-red-500 text-white">&cross;</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
