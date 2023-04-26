<script setup>
  import { computed } from 'vue';
  import css from "./MailInput.module.css";

  const props = defineProps(["styleType"]);

  const classNames = computed(() => ({
    [css.input__main]: props.styleType === "icon",
    [css.input__default]: !props.styleType,
  }))
</script>

<template>
  <div :class="css.input__wrapper">
    <input :class="[classNames]" type="text">
    <span :class="css.input__icon">
    <slot>
      <img src="/search.svg" alt="search">
    </slot>
    </span>
  </div>
</template>
