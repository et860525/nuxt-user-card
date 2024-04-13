<script setup lang="ts">
export interface UserDataField {
  name: string;
  img?: string;
  email: string;
  skill: any;
  intro: string;
}

const props = defineProps<UserDataField>();

// test data
const user_data: UserDataField = {
  name: "Mango",
  img: "",
  email: "example@cc.com",
  skill: ["JS", "TS"],
  intro:
    "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Perferendis necessitatibus quaerat eos porro rerum reiciendis. Impedit delectus cumque velit inventore ea at, labore est saepe quibusdam! Earum quia natus officia?",
};

// Style
const title_list_style = "text-lg font-bold text-primary underline";
</script>

<template>
  <div
    class="p-8 tracking-wide border rounded-lg shadow-lg border-slate-500 shadow-gray-500/50 dark:bg-slate-500 dark:shadow-slate-500/50"
  >
    <div class="text-center">
      <img :src="props.img" class="mx-auto rounded-full w-28 h-28" />
    </div>
    <h2 class="mb-5 text-2xl font-bold text-center">{{ props.name }}</h2>
    <p class="mb-2">
      <span :class="title_list_style">Email:</span> {{ props.email }}
    </p>
    <p class="mb-2">
      <span :class="title_list_style">Skills:</span> {{ props.skill }}
    </p>
    <p><span :class="title_list_style">Intro:</span> {{ props.intro }}</p>
  </div>
</template>
