<script setup>
  import { computed } from 'vue';
  import MailCheckbox from '../Controls/MailCheckbox/MailCheckbox.vue';

  import css from './Letter.module.css';

  const { date } = defineProps(["date", "isImportant"]);
  const stringDate = computed(() => {
    return Intl.DateTimeFormat("ru-RU", { month: "short", day: "numeric", hour: "numeric", minute: "numeric" }).format(date);
  })
</script>

<template>
  <div :class="css.letter">
    <div>
      <MailCheckbox></MailCheckbox>
      <span v-if="isImportant">!</span>
    </div>
    <div class=""><slot name="sender"></slot></div>
    <div class=""><slot name="title"></slot></div>
    

    <div class=""> {{ stringDate }}</div>
  </div>
</template>
