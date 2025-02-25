<template>
  <div :style="[baseStyles, overridingStyles]">Hello Vue</div>
</template>

<script setup lang="ts">
import { reactive } from 'vue'

const baseStyles = reactive({
  color: 'red',
  fontSize: '20px',
})

const overridingStyles = reactive({
  fontSize: '25px',
})
</script>
