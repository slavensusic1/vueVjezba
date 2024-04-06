<script setup>
import { ref } from "vue";

const tasks = ref([
  {
    title: "Task 1",
    description: "Description for Task 1",
    priority: "High",
    level: "To Do",
    date: "2021-10-10",
  },
  {
    title: "Task 2",
    description: "Description for Task 2",
    priority: "Medium",
    level: "In Progress",
    date: "2021-10-10",
  },
  {
    title: "Task 3",
    description: "Description for Task 3",
    priority: "Low",
    level: "To Do",
    date: "2021-10-10",
  },
  {
    title: "Task 4",
    description: "Description for Task 3",
    priority: "Low",
    level: "In Progress",
    date: "2021-10-10",
  },
  {
    title: "Task 5",
    description: "Description for Task 3",
    priority: "Low",
    level: "Done",
    date: "2021-10-10",
  },
  {
    title: "Task 6",
    description: "Description for Task 3",
    priority: "Low",
    level: "Done",
    date: "2021-10-10",
  },
  {
    title: "Task 7",
    description: "Description for Task 3",
    priority: "Low",
    level: "In progress",
    date: "2021-10-10",
  },
  {
    title: "Task 8",
    description: "Description for Task 3",
    priority: "Low",
    level: "Done",
    date: "2021-10-10",
  },
  {
    title: "Task 7",
    description: "Description for Task 3",
    priority: "Low",
    level: "In progress",
    date: "2021-10-10",
  },
  {
    title: "Task 7",
    description: "Description for Task 3",
    priority: "Low",
    level: "In progress",
    date: "2021-10-10",
  },
]);

import InProgress from "./components/InProgress.vue";
import ToDo from "./components/ToDo.vue";
import Done from "./components/Done.vue";
import AddTaskForm from "./AddTaskForm.vue";
const showForm = ref(false);
const showFormHandler = () => {
  showForm.value = !showForm.value;
};
</script>

<template>
  <div class="h-screen w-full bg-gray-400">
    <button
      @click="showFormHandler"
      class="bg-blue-500 text-white p-2 rounded-lg"
    >
      Add Task
    </button>
    <div v-if="showForm">
      <AddTaskForm />
    </div>

    <h1 class="text-blue-950 text-5xl max-w-xl mx-auto">The board</h1>
    <div class="flex justify-between max-w-6xl mx-auto">
      <ToDo :tasks="tasks" />
      <InProgress :tasks="tasks" />
      <Done :tasks="tasks" />
    </div>
  </div>
</template>
