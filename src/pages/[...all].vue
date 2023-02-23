<script setup lang="ts"></script>

<template>
  <div id="not-found" class="flex justify-center items-center">
    <h1 class="text-3xl underline">404 page not found</h1>
  </div>
</template>

<route lang="yaml">
meta:
  layout: 404
</route>

<style lang="scss">
  #not-found {
    height: 100%;
  }
</style>
