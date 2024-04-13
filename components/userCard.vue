<script setup lang="ts">
type UserDataField = {
  name: string;
  email: string;
  skill: any;
  intro: string;
};

const user_data: UserDataField = {
  name: "Mango",
  email: "example@cc.com",
  skill: ["JS", "TS"],
  intro:
    "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Perferendis necessitatibus quaerat eos porro rerum reiciendis. Impedit delectus cumque velit inventore ea at, labore est saepe quibusdam! Earum quia natus officia?",
};
</script>

<template>
  <div
    class="p-5 tracking-wide border border-gray-500 rounded-lg dark:bg-gray-500"
  >
    <h2 class="mb-5 text-2xl font-bold">{{ user_data.name }}</h2>
    <p class="mb-2">
      <span class="text-lg font-bold">Email:</span> {{ user_data.email }}
    </p>
    <p class="mb-2">
      <span class="text-lg font-bold">Skills:</span> {{ user_data.skill }}
    </p>
    <p><span class="text-lg font-bold">Intro:</span> {{ user_data.intro }}</p>
  </div>
</template>
