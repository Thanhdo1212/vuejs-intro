<script setup lang="ts">
const emits = defineEmits(['increase', 'decrease'])
const increaseBySteps = () => {
  emits('increase')
}

const decreaseByStep = () => {
  emits('decrease')
}
</script>

<template>
  <button @click="increaseBySteps">Increase</button>
  <br />
  <button @click="decreaseByStep">Decrease</button>
</template>
