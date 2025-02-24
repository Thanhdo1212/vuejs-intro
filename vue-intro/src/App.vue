<script setup lang="ts">
import { reactive, ref } from 'vue'
const count = ref(0)
const state = reactive({
  count,
})
const updateCount = () => {
  state.count++
}
console.log(state.count)
</script>
<template>
  <p id="count">{{ count }}</p>
  <button @click="updateCount">Tăng</button>
</template>
