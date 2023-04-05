<script setup>
  import { ref, onMounted, onUnmounted }  from 'vue';
  import css from '../../App.module.css';
  const userDiscount = ref(0);
  const interval = ref(0);

  function getRandomInt(min, max) {
  min = Math.ceil(min);
  max = Math.floor(max);
  return Math.floor(Math.random() * (max - min) + min);
}

  onMounted(() => {
    interval.value = setInterval(() => {
      userDiscount.value = getRandomInt(1, 20);
    }, 1000);
  });

  onUnmounted(() => {
    clearInterval(interval.value);
  });


</script>

<template>
    <div :class="css.card">
      <slot :discountForUser="userDiscount"></slot>
    </div>

</template>