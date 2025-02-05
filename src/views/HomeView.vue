<script setup lang="ts">
import Header from '../components/TheHeader.vue';
import Card from '../components/TheCard.vue';
</script>

<template>
  <main>
    <div class="bg-white w-5/6 m-auto rounded-xl shadow-xl shadow-grey-200 my-20">
      <Header />

      <div class="p-10">
        <div class="flex justify-between items-center mb-10">
          <h1 class="text-3xl font-bold">Все тесты</h1>
          <div class="flex items-center gap-4">
            <select
              class="py-2 px-3 border border-gray-200 focus:border-gray-400 rounded-md focus:outline-none"
            >
              <option value="name">По названию</option>
              <option value="price">По баллам (низкие)</option>
              <option value="price">По баллам (высокие)</option>
            </select>
            <div class="relative">
              <input
                type="text"
                class="border border-gray-200 rounded-md py-2 pl-10 pr-4 focus:outline-none focus:border-gray-400"
                placeholder="Поиск..."
              />
              <div class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none">
                <img alt="search bar" src="/src/assets/images/search.svg" />
              </div>
            </div>
          </div>
        </div>

        <div class="grid grid-cols-4 gap-10">
          <Card
            title="Функции"
            price="Математика"
            img="/src/assets/images/lessons/newtons-r.svg"
          />

          <Card
            title="Графы"
            price="Математика"
            img="/src/assets/images/lessons/chemistry-r.svg"
          />

          <Card
            title="Арифметика"
            price="Математика"
            img="/src/assets/images/lessons/calculator-s.svg"
          />

          <Card
            title="Корни"
            price="Математика"
            img="/src/assets/images/lessons/root-r.svg"
          />

          <Card
            title="Правописание"
            price="Грамматика"
            img="/src/assets/images/lessons/magnet-r.svg"
          />
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped>
</style>
