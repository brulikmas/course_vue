<script setup>
  import Snackbar from './components/Snackbar.vue';
  import { ref } from 'vue';
  const isShow = ref(false);
</script>

<template>
  <button @click="isShow = true">Show Snackbar</button>
  <Teleport to="body">
    <Snackbar 
      :show="isShow" 
      @close="isShow = false">
    </Snackbar>
  </Teleport>
  
</template>

<style scoped>

</style>
