<script setup lang="ts">
  import { useRouter } from 'vue-router';
  const router = useRouter();
</script>

<template>
  <div id="layout-404">
    <div class="flex items-center fixed w-full h-12 z-10 top-0 bg-indigo-900 drop-shadow-xl">
      <button class="btn-primary m-2" @click="router.back()">Back</button>
    </div>
    <RouterView />
  </div>
</template>

<style lang="scss">
  #layout-404 {
    height: 100%;
  }
</style>
