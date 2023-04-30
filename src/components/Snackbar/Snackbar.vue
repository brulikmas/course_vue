<script setup>
import css from './Snackbar.module.css';
import { Teleport } from 'vue';
defineEmits(["close"]);
defineProps({
  show: Boolean,
});

</script>

<template>
  <Teleport to="#snackbar">
    <Transition>
      <div v-if="show" :class="css.snackbar">
        <div :class="css.snackbar_body">
          <p>Какая-то подсказка</p>
          <button @click="$emit('close')">&times;</button>
        </div>
      </div>
    </Transition>
  </Teleport>
</template>

<style scoped>

.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>
