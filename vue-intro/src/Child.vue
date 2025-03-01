<script setup lang="ts">
const name = defineModel()
</script>

<template>
  <h1>Component v-model</h1>
  <h1>Your Name : {{ name }}</h1>
  <input v-model="name" placeholder="enter your name" />
</template>
