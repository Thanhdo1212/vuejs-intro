<script setup lang="ts">
import { nextTick, ref } from 'vue'

const count = ref(0)

const updateCount = async () => {
  count.value++
  await nextTick()
  console.log(document.getElementById('count').textContent) // ❌ Không thấy thay đổi ngay lập tức!
}
</script>

<template>
  <p id="count">{{ count }}</p>
  <button @click="updateCount">Tăng</button>
</template>
