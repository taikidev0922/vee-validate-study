<template>
  <div class="form-group">
    <label for="theComboNoSrc">{{ label }}</label>
    <WjComboBox
      id="theComboNoSrc"
      :textChanged="onTextChanged"
      :initialized="onInit"
    ></WjComboBox>
    <div class="text-red">{{ errorMessage }}</div>
  </div>
</template>

<script setup lang="ts">
import { useField } from "vee-validate";
import { WjComboBox } from "@grapecity/wijmo.vue2.input";
import { ComboBox } from "@grapecity/wijmo.input";
const props = defineProps({
  name: {
    type: String,
    required: true,
  },
  label: {
    type: String,
    required: true,
  },
  type: String,
  modelValue: String,
});
const onInit = (e: ComboBox) => {
  e.inputElement.name = props.name;
};
const { value, errorMessage } = useField(() => props.name, undefined, {
  syncVModel: true,
});
const onTextChanged = (e: ComboBox) => {
  value.value = e.text;
};
</script>
