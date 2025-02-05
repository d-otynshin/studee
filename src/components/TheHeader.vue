<template>
  <header class="flex justify-between px-10 py-6">
    <router-link to="/sign-in">
      <div class="flex items-center gap-4">
        <img src="/src/assets/images/studee-logo.png" alt="Logo" class="w-10" />
        <div>
          <h2 class="font-bold text-l uppercase">Studee</h2>
          <p class="text-slate-400">Система выявления точек роста</p>
        </div>
      </div>
    </router-link>

    <ul class="flex items-center gap-10">
      <router-link to="/">
        <li class="flex items-center gap-3 cursor-pointer">
          <img class="w-7" src="/src/assets/icons/test.png" alt="Cart" />
          <span>Тесты</span>
        </li>
      </router-link>
      <li class="flex items-center gap-3 cursor-pointer">
        <img class="w-7" src="/src/assets/icons/heart.png" alt="Favorite" />
        <span>Закладки</span>
      </li>
      <router-link to="/profile">
        <li class="flex items-center gap-3 cursor-pointer">
<!--          profile logo-->
<!--          <img class="w-7" src="/src/assets/icons/profile.png" alt="Profile" />-->
          <img class="w-7" src="/src/assets/images/woman.svg" alt="Profile" />
          <span>Yana G.</span>
        </li>
      </router-link>
    </ul>
  </header>
</template>
<script setup lang="ts">
</script>
