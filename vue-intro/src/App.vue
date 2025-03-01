<script setup lang="ts">
import { provide, ref } from 'vue'
import GrandChild from './GrandChild.vue'

const location = ref('Vietnam')
const changeLocation = () => {
  location.value = 'California, America'
}

// if you want to pass an att but readonly, you can usse readonly()

provide('locate', { location, changeLocation })
</script>

<template>
  <GrandChild />
</template>
