<script setup lang="ts">

defineProps({
  title: String,
  img: String,
  price: Number,
});

</script>

<template>
  <div
    class="flex flex-col w-full border border-slate-100 rounded-xl p-8 cursor-pointer transition hover:shadow-md"
  >
    <img :src="img" class="w-5/6" alt="Sneaker" />
    <p class="pt-4">{{ title }}</p>
    <div class="flex justify-between mt-5">
      <div class="flex flex-col gap-2">
        <span class="text-slate-200">Предмет</span>
        <span class="font-bold">{{ price }}</span>
      </div>
      <img src="/src/assets/images/plus.svg" alt="Plus" />
    </div>
  </div>
</template>
