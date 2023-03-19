<script setup>
  import { reactive, ref, watchEffect } from 'vue';

  const counter = ref(0);
  const date = ref(new Date().toLocaleTimeString());

  watchEffect(() => {
    setInterval(() => {
      date.value = new Date().toLocaleTimeString();
    }, 1000)
  });
</script>

<template>
 <button @click="counter++">counter {{ counter }}</button>
 <h1>{{ date }}</h1>
</template>

<style scoped>

</style>
