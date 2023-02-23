<script setup lang="ts">
import NavComponent from '../components/NavComponent.vue';
</script>

<template>
  <div id="default">
    <NavComponent />
    <RouterView />
  </div>
</template>

<style scoped>
  #default {
    height: 100%;
  }
</style>
