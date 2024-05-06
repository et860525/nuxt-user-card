<script setup lang="ts">
const route = useRoute();

useHead({
  title: `${route.meta.title}`,
  meta: [{ property: "og:title", content: `${route.meta.title}` }],
  bodyAttrs: { class: "bg-slate-100 dark:bg-slate-800" },
});
</script>

<template>
  <div>
    <slot />
  </div>
</template>
