<script setup lang="ts">
import { computed } from 'vue';

interface BaseButtonProps {
  kind?: "default",
  color?: |
    "black" |
    "green" |
    "grey" |
    "purple" |
    "red" |
    "yellow" |
    "white"
}

const props = withDefaults(defineProps<BaseButtonProps>(), {
  kind: "default",
  color: 'black'
});

const kindClass = computed(() => `base-button--${props.kind}`);
const colorClass = computed(() => `base-button--${props.color}`);

</script>

<template>
  <button
    type="button"
    :class="['base-button', kindClass, colorClass]"
  >
    <slot name="beforeText"></slot>
    <slot></slot>
    <slot name="beforeText"></slot>
  </button>
</template>

<style scoped>
.base-button {
  /* TOKENS */

  --base-button-padding: var(--padding-small) var(--padding-medium);
  --base-button-border-radius: var(--border-radius);
  --base-button-border: var(--border-width-small) solid var(--black);
  --base-button-fs: var(--fs-medium);
  --base-button-fw: var(--fw-medium);
  --base-button-color: var(--white);
  --base-button-text-shadow: var(--text-shadow-small);
  --base-button-box-shadow: var(--box-shadow);


  /* PROPERTIES */

  /* kinds */
  &--default {
    box-sizing: border-box;
    border: var(--base-button-border);
    border-radius: var(--base-button-border-radius);
    padding: var(--base-button-padding);
    font-size: var(--base-button-fs);
    font-weight: var(--base-button-fw);
    color: var(--base-button-color);
    text-shadow: var(--base-button-text-shadow);
    box-shadow: var(--base-button-box-shadow);
    transform: translate(5px, -5px);
    transition-duration: .2s;
  }

  /* colors */

  &--black {
    background-color: var(--black);
  }
  &--green {
    background-color: var(--green);
  }
  &--grey {
    background-color: var(--grey);
  }
  &--purple {
    background-color: var(--purple);
  }
  &--red {
    background-color: var(--red);
  }

  &--yellow {
    background-color: var(--yellow);
  }

  &--white {
    background-color: var(--white);
  }

  /* state */

  &:hover {
    cursor: pointer;
  }

  &:active {
  box-shadow: none;
  transform: translate(-0px, 0px);
}
}
</style>
