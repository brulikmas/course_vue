<script setup>
  import { ref }  from 'vue';
  import css from '../../App.module.css';
  import OneCard from './OneCard.vue';

  const textForFind = ref('');
  const cards = [
    {
      name: 'Book',
      price: '5$',
    },
    {
      name: 'Phone',
      price: '150$',
    },
    {
      name: 'Table',
      price: '75$',
    },
    {
      name: 'Box',
      price: '1$',
    }
  ]

  function findCard(card) {
    return card.name.toLowerCase().includes(textForFind.value.toLowerCase());
  }

</script>

<template>
  <input :class="css.input" v-model="textForFind">
  <template v-for="(item, index) in cards" :key="index">
    <OneCard v-if="findCard(item)" v-slot="{ discountForUser }">
      <h2>{{ item.name }}</h2>
      <p>{{ item.price }} Your discount: {{ discountForUser }}</p>
    </OneCard>
  </template>

</template>