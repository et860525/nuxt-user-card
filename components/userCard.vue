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
    class="p-8 tracking-wide transition ease-in-out rounded-lg shadow-md bg-slate-300 border-slate-500 shadow-gray-400/50 dark:bg-slate-500 dark:shadow-slate-500/50"
  >
    <div class="mb-1 text-center">
      <img :src="props.img" class="mx-auto rounded-full w-28 h-28" />
    </div>
    <h2 class="mb-5 text-2xl font-bold text-center">{{ props.name }}</h2>
    <p class="mb-2">
      <span :class="title_list_style">Email:</span> {{ props.email }}
    </p>
    <p class="mb-2">
      <!-- <span :class="title_list_style">Skills:</span> {{ props.skill }} -->
      <span :class="title_list_style" class="align-bottom">Skills:</span>&nbsp;
      <UIcon name="i-logos-javascript" size="30px" dynamic />
      <UIcon name="i-logos-typescript-icon" class="ml-2" size="30px" dynamic />
    </p>
    <p><span :class="title_list_style">Intro:</span> {{ props.intro }}</p>
  </div>
</template>
