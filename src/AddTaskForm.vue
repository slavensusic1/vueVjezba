<script setup>
import { ref } from "vue";

const title = ref("");
const description = ref("");
const priority = ref("");
const level = ref("");
const date = ref("");
const addTask = () => {
  tasks.value.push({
    title: title.value,
    description: description.value,
    priority: priority.value,
    level: level.value,
    date: date.value,
  });
  title.value = "";
  description.value = "";
  priority.value = "";
  level.value = "";
  date.value = "";
};
</script>

<template>
  <div class="bg-gray-200 flex items-center justify-center w-full h-screen">
    <div class="p-4 bg-white rounded-lg shadow-md">
      <form @submit.prevent="addTask" class="space-y-4">
        <div>
          <label for="title" class="block text-sm font-medium text-gray-700"
            >Title</label
          >
          <input
            type="text"
            id="title"
            v-model="title"
            class="mt-1 block w-full shadow-sm focus:ring-blue-500 focus:border-blue-500 border-gray-300 rounded-md"
          />
        </div>
        <div>
          <label
            for="description"
            class="block text-sm font-medium text-gray-700"
            >Description</label
          >
          <select
            id="description"
            v-model="description"
            rows="3"
            class="mt-1 block w-full shadow-sm focus:ring-blue-500 focus:border-blue-500 border-gray-300 rounded-md"
          >
            <option>To do</option>
            <option>In progress</option>
            <option>Done</option>
          </select>
        </div>
        <div>
          <label for="priority" class="block text-sm font-medium text-gray-700"
            >Priority</label
          >
          <input
            type="text"
            id="priority"
            v-model="priority"
            class="mt-1 block w-full shadow-sm focus:ring-blue-500 focus:border-blue-500 border-gray-300 rounded-md"
          />
        </div>
        <div>
          <label for="level" class="block text-sm font-medium text-gray-700"
            >Level</label
          >
          <input
            type="text"
            id="level"
            v-model="level"
            class="mt-1 block w-full shadow-sm focus:ring-blue-500 focus:border-blue-500 border-gray-300 rounded-md"
          />
        </div>
        <div>
          <label for="date" class="block text-sm font-medium text-gray-700"
            >Date</label
          >
          <input
            type="date"
            id="date"
            v-model="date"
            class="mt-1 block w-full shadow-sm focus:ring-blue-500 focus:border-blue-500 border-gray-300 rounded-md"
          />
        </div>
        <div>
          <button
            type="submit"
            class="w-full flex justify-center py-2 px-4 border border-transparent rounded-md shadow-sm text-sm font-medium text-white bg-blue-600 hover:bg-blue-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-500"
          >
            Add Task
          </button>
        </div>
      </form>
    </div>
  </div>
</template>
