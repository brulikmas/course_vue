<script setup>
  import Letter from "../Letter/Letter.vue";
  import { lettersMock } from "../../utils/mock.js";
  import css from "./Main.module.css";
</script>

<template>
  <main :class="css.main">
    <aside></aside>
    <section :class="css.letters">
      <Letter v-for="{ date, title, sender, isImportant} in lettersMock"
        :date="date"
        :isImportant="isImportant"
      >
        <template #title>{{ title }}</template>
        <template #sender>{{ sender }}</template>
      </Letter>
    </section>
  </main>
</template>

