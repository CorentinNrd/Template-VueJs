<script setup lang="ts"></script>

<template>
  <div id="index" class="flex justify-center items-center">
    <div class="flex flex-col items-center">
      <h1 class="text-3xl underline mb-3">Hello world!</h1>
      <p class="text-xl mb-3">Template Vue + Vite + TailwindCSS</p>
      <div class="block-image mb-3">
        <img src="../assets/vue.svg" alt="Vue Logo" class="h-20 mb-3" />
        <img src="../assets/vite.svg" alt="Vite Logo" class="h-20 mb-3" />
        <img src="../assets/tailwind.svg" alt="Tailwind Logo" class="h-20 mb-3" />
      </div>
      <p class="text-sm italic text-slate-400">By Corentin Nordmann</p>
    </div>
  </div>
</template>

<style lang="scss">
  #index {
    height: 100%;
    .block-image {
      display: flex;
      align-items: center;
      img {
        margin: 0 1rem;
        width: 4rem;
        height: 4rem;
        object-fit: contain;
      }
    }
  }
</style>
