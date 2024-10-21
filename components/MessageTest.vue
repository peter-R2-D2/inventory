<template>
  <h1>Mensaje de prueba: {{ message }}</h1>
</template>

<script setup>
const props = defineProps({
  message: {
    type: String,
    required: true,
  },
});
</script>

<style>
</style>