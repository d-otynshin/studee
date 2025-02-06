<script setup lang="ts">
import Header from '../components/TheHeader.vue';
import { ref, computed, onMounted } from 'vue'

const question = "Четыре простых числа расположены в порядке возрастания. Сумма первых трех равна 385, а последней — 1001."
const options = ref(["11", "13", "17", "9"])
const selected = ref(null)

const totalSteps = 10
const currentStep = ref(2)

const nextStep = () => {
  if (currentStep.value < totalSteps) currentStep.value++;
};

const prevStep = () => {
  if (currentStep.value > 1) currentStep.value--;
};

const setCurrentStep = (n: number) => {
  currentStep.value = n
}

const timeRemaining = ref(12400); // (in seconds)
const timer = null;

const formattedTime = computed(() => {
  const hours = Math.floor(timeRemaining.value / 3600);
  const minutes = Math.floor((timeRemaining.value % 3600) / 60);
  const seconds = timeRemaining.value % 60;
  return `${hours.toString().padStart(2, "0")}:${minutes.toString().padStart(2, "0")}:${seconds.toString().padStart(2, "0")}`;
});

const startTimer = () => {
  timer = setInterval(() => {
    if (timeRemaining.value > 0) {
      timeRemaining.value--;
    } else {
      clearInterval(timer);
    }
  }, 1000);
};

</script>

<template>
  <main>
    <div class="bg-white w-5/6 m-auto rounded-xl shadow-xl shadow-grey-200 my-10">
      <Header />

      <div class="p-10">
        <div class="flex justify-between items-center mb-10">
          <h1 class="text-3xl font-bold">Тестирование</h1>
        </div>

        <div class="flex justify-between items-center mb-6">
          <div class="flex gap-4 bg-white p-4">
          <span class="py-2">
            <svg class="w-10 h-10 text-black" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" d="M12 6v6l4 2m5-2a9 9 0 11-9-9 9 9 0 019 9z"/>
          </svg>
          </span>

            <div>
              <!-- Time Remaining Label -->
              <span class="text-lg font-medium text-gray-700">Time remaining</span>

              <!-- Timer Display with Icon -->
              <div class="flex items-center gap-2 text-xl font-semibold text-black">
                <span>{{ formattedTime }}</span>
              </div>
            </div>
          </div>


          <button class="px-12 py-3 bg-black text-white rounded-lg font-medium hover:bg-gray-800 transition">
            Submit
          </button>
        </div>

        <div class="grid grid-cols-6 gap-4 w-full">
          <div class="col-span-4 max-w-2xl p-8 bg-white border border-slate-100 rounded-xl">
            <h2 class="text-2xl font-semibold text-gray-900">{{ question }}</h2>

            <div class="mt-6 grid grid-cols-2 gap-4">
              <label
                v-for="(option, index) in options"
                :key="index"
                class="flex items-center gap-3 p-4 border rounded-xl cursor-pointer transition-all"
                :class="selected === option ? 'bg-gray-200 border-black' : 'hover:bg-gray-100'"
              >
                <input type="radio" v-model="selected" :value="option" class="hidden" />
                <div class="w-6 h-6 flex items-center justify-center border-2 rounded-full transition-all"
                     :class="selected === option ? 'border-black' : 'border-gray-400'">
                  <div v-if="selected === option" class="w-3 h-3 bg-black rounded-full"></div>
                </div>
                <span class="text-lg font-medium text-gray-800">{{ option }}</span>
              </label>
            </div>
          </div>

          <div class="col-span-2 m-auto">
            <div class="relative w-48 h-48 flex items-center justify-center">
              <svg class="w-full h-full transform -rotate-90" viewBox="0 0 100 100">
                <!-- Background Circle -->
                <circle cx="50" cy="50" r="45" stroke="gray" stroke-width="10" fill="none" class="opacity-20"/>
                <!-- Progress Arc -->
                <circle
                  cx="50"
                  cy="50"
                  r="45"
                  stroke="black"
                  stroke-width="10"
                  fill="none"
                  stroke-dasharray="280"
                  :stroke-dashoffset="280 - (280 * currentStep / totalSteps)"
                  stroke-linecap="round"
                  class="transition-all duration-300"
                />
              </svg>
              <!-- Step Counter -->
              <span class="absolute text-xl font-semibold text-gray-900">
                {{ currentStep }}/{{ totalSteps }}
              </span>
            </div>
          </div>
        </div>

        <div class="flex items-center gap-4 mt-12 ml-2">
          <!-- Prev Button -->
          <button
            class="w-12 h-12 border border-slate-100 text-gray-700 rounded-xl font-medium text-lg disabled:bg-gray-300"
            :disabled="currentStep === 1"
            @click="prevStep"
          >
            ‹
          </button>

          <!-- Pagination Dots -->
          <div class="flex items-center gap-2">
            <span
              v-for="n in totalSteps"
              :key="n"
              class="cursor-pointer w-12 h-12 flex items-center justify-center border border-slate-100 rounded-xl font-medium text-lg"
              :class="n === currentStep ? 'bg-gray-200 border-black' : 'hover:bg-gray-100'"
              @click="setCurrentStep(n)"
            >
              {{ n }}
            </span>
          </div>

          <!-- Next Button -->
          <button
            class="w-12 h-12 border border-slate-100 text-gray-700 rounded-xl font-medium text-lg disabled:bg-gray-300"
            :disabled="currentStep === totalSteps"
            @click="nextStep"
          >
            ›
          </button>
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped>
</style>
