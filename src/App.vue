<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>

<template>
  <header class="my-2">
    <nav class="flex gap-x-3">
      <RouterLink class="text-lg" to="/">Home</RouterLink>
      <RouterLink class="text-lg" to="/about">About</RouterLink>
    </nav>
  </header>
  <hr />

  <main class="my-4">
    <RouterView />
  </main>
</template>

<style>
#app {
  @apply container mx-auto;
}
</style>
