<script setup>
import { RouterLink, RouterView } from "vue-router";
import { useDark, useToggle } from "@vueuse/core";

const isDark = useDark();
const toggleDark = useToggle(isDark);

const toggleColorScheme = () => {
  toggleDark();

  const element = document.querySelector("html");
  element.classList.toggle("dark");
};
</script>

<template>
  <p>Dark theme: {{ isDark }}</p>
  <Button label="Toggle Color Scheme" @click="toggleColorScheme()" />

  <RouterView />
</template>

<style scoped>

</style>
