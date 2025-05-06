<template>
    <div class="min-h-screen flex flex-col bg-bg-secondary text-text-primary">
      <LayoutHeader />
      <main class="">
        <slot />
      </main>
      <LayoutFooter />
    </div>
  </template>
  <script setup lang="ts">
  </script>