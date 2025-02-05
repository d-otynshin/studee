<script setup lang="ts">
import Header from '../components/TheHeader.vue';
import { ref } from 'vue'

const activeTab = ref(0)

const tabs = ref([
  { label: 'Тесты', content: 'This is the overview content.' },
  { label: 'Предметы', content: 'Here are some amazing features of our product.' },
  { label: 'Календарь', content: 'Our pricing is simple and transparent.' }
])
</script>

<template>
  <main>
    <div class="bg-white w-5/6 m-auto rounded-xl shadow-xl shadow-grey-200 my-20">
      <Header />

      <div class="p-10">
        <div class="flex justify-between items-center mb-10">
          <h1 class="text-3xl font-bold">Профиль</h1>
        </div>

        <div class="grid grid-cols-6 gap-4 w-full">
          <div class="col-span-4 relative flex flex-col border border-slate-100 rounded-xl pt-14 px-8 cursor-pointer">
            <div class="w-full h-48 bg-blue-400 absolute top-0 right-0 left-0 z-0 rounded-t-xl"></div>
            <div class="z-10">
              <img class="ml-6 w-52 rounded-[50%] border-8 border-white" src="/src/assets/images/woman.svg" alt="Profile Picture" />
              <div class="p-6">
                <h2 class="text-2xl font-semibold text-gray-900">Yana Gabrielyan</h2>
                <p class="text-gray-600 text-sm">SpaceX</p>
                <div class="mt-4">
                  <p class="text-gray-800 font-medium">Email: <span class="text-gray-600">gabrielyan@spacex.com</span></p>
                  <p class="text-gray-800 font-medium">Location: <span class="text-gray-600">Sim City</span></p>
                </div>
                <div class="mt-6 flex items-center space-x-4">
                  <a class="w-8" :href="123" target="_blank" rel="noopener noreferrer">
                    <img src="/src/assets/images/socials/telegram.svg" alt="telegram" />
                  </a>
                  <a class="w-8" :href="123" target="_blank" rel="noopener noreferrer">
                    <img src="/src/assets/images/socials/twitter.svg" alt="twitter" />
                  </a>
                </div>
              </div>

            </div>
          </div>

          <div class="col-span-2 border border-slate-100 rounded-xl p-4">
            <h2 class="text-xl font-semibold text-gray-900">Название</h2>
            <p class="text-gray-600 mt-2">Описание</p>
          </div>

          <div class="col-span-4">
            <!-- Tabs Header -->
            <div class="flex border border-slate-100 rounded-xl py-2">
              <button
                v-for="(tab, index) in tabs"
                :key="index"
                @click="activeTab = index"
                class="py-2 mx-4 font-medium text-gray-600 border-b-2 transition-all"
                :class="activeTab === index ? 'text-blue-500 border-blue-500' : 'border-transparent hover:text-blue-500'"
              >
                {{ tab.label }}
              </button>
            </div>

            <!-- Tabs Content -->
            <div class="p-4 bg-white border border-slate-100 rounded-xl mt-4 h-28">
              <p class="text-gray-700">{{ tabs[activeTab].content }}</p>
            </div>
          </div>
          <div class="col-span-2 border border-slate-100 rounded-xl h-28 p-4">
            <h2 class="text-xl font-semibold text-gray-900">Название</h2>
            <p class="text-gray-600 mt-2">Описание</p>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped>
</style>
