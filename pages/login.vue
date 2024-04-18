<script setup lang="ts">
useHead({
  title: "Login",
  meta: [{ name: "description", content: "Login page." }],
});
</script>

<template>
  <div class="max-w-2xl p-5 mx-auto">
    <Navbar />
    <div class="flex justify-center gap-2 mb-5">
      <h1 class="text-2xl font-bold text-center">Login Page</h1>
      <DarkModeToggle />
    </div>
  </div>
</template>