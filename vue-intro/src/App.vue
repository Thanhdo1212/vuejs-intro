<script setup lang="ts">
import { ref } from 'vue'
import children from './children.vue'
const count = ref(0)

//event component

const increase = () => {
  count.value++
}

const decrease = () => {
  count.value--
}
</script>

<template>
  <h1>Props in Vuejs</h1>

  <h1>Count is : {{ count }}</h1>
  <children @increase="increase" @decrease="decrease" />
</template>
