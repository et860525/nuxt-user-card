<script setup lang="ts">
import type { UserDataField } from "../components/userCard.vue";

definePageMeta({
  title: "User Card",
});

const user_data: UserDataField = {
  name: "Mango",
  img: "https://avatars.githubusercontent.com/u/739984?v=4",
  email: "example@cc.com",
  skill: ["JS", "TS"],
  intro:
    "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Perferendis necessitatibus quaerat eos porro rerum reiciendis. Impedit delectus cumque velit inventore ea at, labore est saepe quibusdam! Earum quia natus officia?",
};
</script>

<template>
  <div class="max-w-2xl p-5 mx-auto">
    <Navbar />
    <div class="flex justify-center gap-2 mb-5">
      <h1 class="text-2xl font-bold text-center">User Card</h1>
      <DarkModeToggle />
    </div>
    <UserCard
      :name="user_data.name"
      :img="user_data.img"
      :email="user_data.email"
      :skill="user_data.skill"
      :intro="user_data.intro"
    />
  </div>
</template>
