<script setup>
  import { ref }  from 'vue';
  import css from '../../App.module.css';

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

</script>

<template>
  <input :class="css.input" v-model="textForFind">
  <template v-for="(item, index) in cards" :key="index">
    <div :class="css.card" v-if="item.name.includes(textForFind)">
      <h2>{{ item.name }}</h2>
      <p>{{ item.price }}</p>
    </div>
  </template>

</template>