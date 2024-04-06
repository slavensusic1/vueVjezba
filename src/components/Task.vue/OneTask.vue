<script setup>
import { ref, computed } from "vue";
defineProps(["title", "description", "priority", "level", "date"]);
const showToggler = ref(false);
const showTrigger = () => {
  showToggler.value = !showToggler.value;
};
const expandIcon = computed(() => {
  return showToggler.value ? "-" : "+";
});
</script>

<template>
  <div class="bg-gray-700 px-2 py-2 text-center min-w-72 min-h-24-h-max">
    <h2 class="text-gray-200 text-2xl">{{ title }}</h2>
    <button @click="showTrigger">{{ expandIcon }}</button>
    <p
      v-if="showToggler"
      class="text-gray-200 text-center max-w-64 text-sm max-h-[2rem] overflow-y-hidden"
    >
      {{ description }}
    </p>
    <div class="flex justify-between items-center">
      <p>{{ priority }}</p>
      <span class=""> {{ level }}</span>
    </div>
    <div class="text-left pt-5 text-sky-100">{{ date }}</div>
  </div>
</template>
