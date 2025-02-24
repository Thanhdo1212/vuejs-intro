<script setup lang="ts">
import { ref } from 'vue'
const msg = ref('xin chao vue 3')
const changeMsg = () => (msg.value = 'xin chao vue 4')

// deep reactivity

const obj = ref({
  nested: { count: 0 },
  arr: ['foo', 'bar'],
})
const mutateDeeply = () => {
  // những thay đổi này sẽ hoạt động như mong đợi.
  obj.value.nested.count++
  obj.value.arr.push('baz')
}
</script>

<template>
  <div>
    <h1>{{ msg }}</h1>
    <h2>{{ obj }}</h2>
    <button @click="changeMsg">Change message</button>
    <button style="height: 50px; width: 200px" @click="mutateDeeply">mutate Deeply</button>
  </div>
</template>
