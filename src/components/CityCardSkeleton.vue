<template>
  <div class="bg-teal-600 p-4 rounded-xl shadow-md">
    <div class="bg-orange-100 rounded-lg p-4">
      <div class="flex justify-between items-center mb-4">
        <AnimatedPlaceholder class="h-6 w-20" />
        <AnimatedPlaceholder class="h-16 w-20" />
      </div>
      <AnimatedPlaceholder class="h-4 w-16 mb-2" />
      <AnimatedPlaceholder class="h-4 w-32 mb-1" />
      <AnimatedPlaceholder class="h-3 w-24 mb-2" />
      <div class="flex justify-between">
        <AnimatedPlaceholder class="h-3 w-24" />
        <AnimatedPlaceholder class="h-3 w-24" />
      </div>
    </div>

    <div class="mt-4 bg-gray-200 bg-opacity-50 rounded-lg p-4">
      <div class="grid grid-cols-5 gap-2">
        <div v-for="i in 5" :key="i" class="flex flex-col items-center">
          <AnimatedPlaceholder class="h-3 w-8 mb-2" />
          <AnimatedPlaceholder class="h-6 w-6 mb-2" />
          <AnimatedPlaceholder class="h-3 w-6" />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import AnimatedPlaceholder from "./AnimatedPlaceholder.vue";
</script>