<script setup>
import { defineProps, computed } from "vue";
import OneTask from "./Task.vue/OneTask.vue";
const props = defineProps(["tasks"]);
console.log(props.tasks);

const filteredTasks = computed(() => {
  return props.tasks.filter((task) => task.level === "To Do");
});
</script>

<template>
  <div class="flex flex-col justify-start items-center">
    <h1>To Do</h1>
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

<!-- <h2>{{ task.title }}</h2>
<p>{{ task.description }}</p>
<p>{{ task.priority }}</p>
<p>{{ task.level }}</p> -->
