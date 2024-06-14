<template>
  <div class="bg-teal-600 p-4 rounded-xl shadow-lg max-w-sm w-full mx-auto">
    <div class="bg-orange-100 rounded-lg p-4">
      <div class="flex justify-between items-center mb-4">
        <h2 class="text-xl font-semibold text-gray-700">Today</h2>
        <div class="text-5xl font-bold text-orange-500 flex items-center">
          <span class="mr-2">☀️</span>
          {{ Math.round(city.weather.main.temp) }}°
        </div>
      </div>
      <p class="text-orange-600 mb-2">{{ city.weather.weather[0].main }}</p>
      <p class="text-gray-600 text-sm">{{ city.city }}, {{ city.state }}</p>
      <p class="text-gray-500 text-xs">{{ new Date().toLocaleDateString() }}</p>
      <div class="flex justify-between text-xs text-gray-500 mt-2">
        <span>Feels like {{ Math.round(city.weather.main.feels_like) }}°</span>
        <span>Sunset {{ new Date(city.weather.sys.sunset * 1000).toLocaleTimeString([], {hour: '2-digit', minute:'2-digit'}) }}</span>
      </div>
    </div>

    <div class="mt-4 bg-gray-200 bg-opacity-50 rounded-lg p-4">
      <div class="grid grid-cols-5 gap-2 text-center">
        <div v-for="hour in [1, 2, 3, 4, 5]" :key="hour" class="text-white">
          <div class="text-xs mb-1">{{ hour }}AM</div>
          <div class="text-sm">🌤️</div>
          <div class="text-xs mt-1">{{ Math.round(city.weather.main.temp - hour) }}°</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  city: {
    type: Object,
    default: () => {},
  },
});
</script>