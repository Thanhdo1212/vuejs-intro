<script setup lang="ts">
import { inject } from 'vue'

const { location, changeLocation } = inject('locate')
</script>

<template>
  <h1>{{ location }}</h1>
  <button @click="changeLocation">Change Location</button>
</template>
