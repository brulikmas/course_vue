<script setup>
  import { computed } from 'vue';
  import css from "./MailButton.module.css";

  const props = defineProps(["styleType"]);

  const classNames = computed(() => ({
    [css.btn__icon]: props.styleType === "icon",
    [css.btn__default]: !props.styleType,
  }))
</script>

<template>
  <button :class="[classNames, css.btn]"><slot></slot></button>
</template>