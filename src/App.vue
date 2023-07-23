<script setup>

import { ref } from "vue";

const sliders = ref([
  {
    name: 'Beautiful Bangladesh',
    path: '/images/slider-1.jpg',
  },
  {
    name: 'Sajek Valley',
    path: '/images/slider-2.jpg',
  },
  {
    name: 'Tanguar haor',
    path: '/images/slider-3.jpg',
  },
])

const sliderIndex = ref(0)

function prevSlider() {
  if (sliderIndex.value) {
    sliderIndex.value--
  } else {
    sliderIndex.value = sliders.value.length - 1
  }
}

function nextSlider() {
  if (sliderIndex.value < sliders.value.length - 1) {
    sliderIndex.value++
  } else {
    sliderIndex.value = 0
  }
}
</script>

<template>
    <main class="min-h-screen w-full py-20 px-5 flex items-center justify-center bg-gray-900">
      <!-- Slider wrapper -->
      <div class="w-full max-w-6xl relative">
        <h1 class="text-white py-6 text-center text-3xl">Vue.js 3 Carousel Slider Example</h1>
        <!-- Single Slider -->
        <div v-show="sliderIndex === index" v-for="(slider, index) in sliders"
             :key="index">
          <img :src="slider.path" alt="car"
               class="w-full h-[30rem] object-cover rounded-lg shadow">
          <p class="text-center mt-3 text-gray-200 text-xl ">
            {{ slider.name }}
          </p>
        </div>
        <!-- Single Slider end -->

        <!-- Arrows prev -->
        <button @click="prevSlider" class="w-10 h-10 rounded-full bg-gray-400 hover:shadow-lg active:scale-90 transition absolute left-2 top-[20rem] text-gray-700 flex items-center justify-center opacity-50 hover:opacity-100">
          <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor"
               class="w-6 h-6">
            <path stroke-linecap="round" stroke-linejoin="round" d="M15.75 19.5L8.25 12l7.5-7.5"/>
          </svg>
        </button>
        <!-- Arrows prev end -->

        <!-- Arrows next -->
        <button @click="nextSlider" class="w-10 h-10 rounded-full bg-gray-400 hover:shadow-lg active:scale-90 transition absolute right-2 top-[20rem] text-gray-700 flex items-center justify-center opacity-50 hover:opacity-100">
          <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor"
               class="w-6 h-6">
            <path stroke-linecap="round" stroke-linejoin="round" d="M8.25 4.5l7.5 7.5-7.5 7.5"/>
          </svg>
        </button>
        <!-- Arrows next end -->

      </div>
    </main>

</template>

<style scoped>

</style>
