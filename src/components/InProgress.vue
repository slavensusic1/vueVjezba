<script setup>
import { defineProps, computed, watch } from "vue";
import OneTask from "./Task.vue/OneTask.vue";
const props = defineProps(["tasks"]);
console.log(props.tasks);
const filteredTasks = computed(() => {
  return props.tasks.filter((task) => task.level === "In progress");
});
watch(filteredTasks);
</script>

<template>
  <div class="flex flex-col justify-center items-center">
    <h1>In progress</h1>
    <div class="flex flex-col space-y-10">
      <OneTask
        v-for="task in filteredTasks"
        :title="task.title"
        :description="task.description"
        :priority="task.priority"
        :level="task.level"
        :date="task.date"
      />
    </div>
  </div>
</template>

<!-- title: "Task 7",
description: "Description for Task 3",
priority: "Low",
level: "To Do",
date: "2021-10-10" -->
