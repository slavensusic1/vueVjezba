<script setup>
import { computed, watch, defineProps } from "vue";
import OneTask from "./Task.vue/OneTask.vue";
const props = defineProps(["tasks"]);
console.log(props.tasks);
0.0;
const filteredTasks = computed(() => {
  return props.tasks.filter((task) => task.level === "Done");
});
watch(filteredTasks);
</script>

<template>
  <div class="flex flex-col justify-center items-start">
    <h1>Done</h1>
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
