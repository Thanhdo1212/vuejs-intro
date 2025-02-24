<script setup lang="ts">
import { computed, ref } from 'vue'
// writable computed
const firstName = ref('Do Duc')
const lastName = ref('Thanh')

const fullName = computed({
  get() {
    return firstName.value + ' ' + lastName.value
  },
  set(newName) {
    ;[firstName.value, lastName.value] = newName.split(',')
  },
})

const changeName = () => {
  fullName.value = 'Pham Khanh,Ly'
}
</script>
<template>
  <h1>Your Name : {{ fullName }}</h1>
  <button @click="changeName">Change Your Name</button>
</template>
