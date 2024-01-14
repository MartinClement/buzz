<script setup lang="ts">
import BaseButton from "./components/fonctional/BaseButton.vue";

const colors = [
  "black",
  "green",
  "grey",
  "purple",
  "red",
  "yellow",
  "white"
] as ("black" |
  "green" |
  "grey" |
  "purple" |
  "red" |
  "yellow" |
  "white"
)[]
</script>

<template>
  <div class="wrapper">
    <BaseButton
      v-for="color in colors"
      :key="color"
      :color="color"
    >Coucou</BaseButton>
  </div>
</template>

<style scoped>
.wrapper {
  display: flex;
  min-height: 100%;
  justify-content: center;
  align-items: center;
  background: var(--blue-to-orange);
}
</style>
