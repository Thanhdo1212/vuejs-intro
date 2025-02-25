<script setup lang="ts">
import { ref } from 'vue'
const count = ref(0)
const sayHello = (name: string) => {
  alert(`Hello ${name}`)
}
</script>

<template>
  <h1>{{ count }}</h1>
  <button @click="count++">Increase</button>
  <br />
  <button @click="sayHello('Thanh')">Say Hello</button>
</template>
