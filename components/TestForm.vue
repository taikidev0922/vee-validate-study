<template>
    <Form @submit="submit" :validation-schema="validationSchema">
      <Field name="field" style="border: 1px solid;" />
      <ErrorMessage name="field" />
      <button>submit</button>
    </Form>
  </template>
  <script setup>
  import { Field, Form, ErrorMessage } from 'vee-validate';
  import * as yup from 'yup';

  const validationSchema = yup.object({
    field: yup.string().required('必須ですよ'),
  });

  const submit = (event) => {
    console.log(event)
  }
  </script>

