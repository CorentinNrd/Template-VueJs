<script setup lang="ts"></script>

<template>
  <nav id="navbar" class="flex items-center fixed w-full h-12 z-10 top-0 bg-indigo-900 drop-shadow-xl">
    <ul class="flex justify-between items-center w-full px-3">
      <li class="text-white">
        <router-link to="/">
          <button class="btn-primary">Home</button>
        </router-link>
      </li>
      <li class="text-white">
        <router-link to="/contact">
          <button class="btn-primary">Contact</button>
        </router-link>
      </li>
    </ul>
  </nav>
</template>
