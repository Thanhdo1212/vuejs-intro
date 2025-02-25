<script setup lang="ts">
import { ref } from 'vue'
const fruit = ref([
  {
    name: 'apple',
    price: 12,
    isSoldOut: '',
  },
  {
    name: 'orange',
    price: 10,
    isSoldOut: false,
  },
  {
    name: 'banana',
    price: 8,
    isSoldOut: false,
  },
])
</script>

<template>
  <div>
    <ul>
      <!-- v-for with v-if -->
      <template v-for="qua in fruit" :key="qua.name">
        <li v-if="qua.isSoldOut == false">{{ qua.name }} and {{ qua.price }}</li>
      </template>
    </ul>
  </div>
</template>
