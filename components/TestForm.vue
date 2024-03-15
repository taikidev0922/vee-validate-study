<script setup lang="ts">
import InputText from "@/components/ui/InputText.vue";
import * as yup from "yup";
import { toTypedSchema } from "@vee-validate/yup";
import { useForm } from "vee-validate";
const { handleSubmit } = useForm({
  validationSchema: toTypedSchema(
    yup.object({
      email: yup.string().required().email(),
      password: yup.string().required().min(6),
    })
  ),
});

const onSubmit = handleSubmit((values) => {
  console.log(values);
});
</script>

<template>
  <form @submit="onSubmit">
    <InputText name="email" label="email" />
    <InputText name="password" type="password" label="password" />
    <button type="submit">Submit</button>
  </form>
</template>
