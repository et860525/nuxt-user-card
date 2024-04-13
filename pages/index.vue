<script setup lang="ts">
useHead({
  title: "User Card",
  meta: [{ name: "description", content: "My amazing site." }],
});
</script>

<template>
  <div class="max-w-2xl p-5 mx-auto">
    <h1 class="mb-5 text-2xl font-bold text-center">User Card</h1>
    <UserCard />
    <DarkModeToggle />
  </div>
</template>
