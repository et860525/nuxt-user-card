<script setup lang="ts">
import { z } from "zod";
import type { FormError, FormSubmitEvent } from "#ui/types";
useHead({
  title: "Login",
  meta: [{ name: "description", content: "Login page." }],
});

const schema = z
  .object({
    email: z.string().email("Invalid email"),
    password: z.string().min(8, "Must be at least 8 characters"),
    confirmPassword: z.string().min(8),
  })
  .refine((data) => data.password === data.confirmPassword, {
    message: "Password don't match",
    path: ["confirmPassword"],
  });

type Schema = z.output<typeof schema>;

const state = reactive({
  email: undefined,
  password: undefined,
  confirmPassword: undefined,
});

const validate = (state: any): FormError[] => {
  const errors = [];
  if (state.confirmPassword !== state.password)
    errors.push({ path: "confirmPassword", message: "Password don't match" });
  return errors;
};

async function onSubmit(event: FormSubmitEvent<Schema>) {
  // Do something with data
  console.log(event.data.email);
}
</script>

<template>
  <div class="max-w-2xl p-5 mx-auto tracking-wider">
    <Navbar />
    <div class="flex justify-center gap-2 mb-5">
      <h1 class="text-2xl font-bold text-center">Sign Up</h1>
      <DarkModeToggle />
    </div>
    <UForm
      :validate="validate"
      :schema="schema"
      :state="state"
      class="space-y-4"
      @submit="onSubmit"
    >
      <UFormGroup label="Email" name="email" size="lg">
        <UInput v-model="state.email" />
      </UFormGroup>

      <UFormGroup label="Password" name="password" size="lg">
        <UInput v-model="state.password" type="password" />
      </UFormGroup>

      <UFormGroup label="Re-password" name="confirmPassword" size="lg">
        <UInput v-model="state.confirmPassword" type="password" />
      </UFormGroup>

      <UButton type="submit"> Submit</UButton>
    </UForm>
  </div>
</template>
