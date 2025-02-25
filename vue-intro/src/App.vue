<script setup lang="ts">
import { ref } from 'vue'

const userStatus = ref('online')
const changeUserStatus = () => {
  if (userStatus.value === 'online') {
    userStatus.value = 'offline'
  } else if (userStatus.value === 'offline') {
    userStatus.value = 'busy'
  } else if (userStatus.value === 'busy') {
    userStatus.value = 'online'
  }
}
</script>

<template>
  <div>
    <button
      @click="changeUserStatus"
      style="
        padding: 20px;
        color: aliceblue;
        background-color: blueviolet;
        border-radius: 10px;
        font-size: large;
        box-shadow: inset;
        width: 200px;
      "
    >
      Change User Status
    </button>

    <h1 v-if="userStatus === 'online'">User is online</h1>
    <h1 v-else-if="userStatus === 'offline'">User is offline</h1>
    <h1 v-else-if="userStatus === 'busy'">user is busy</h1>
    <h1 v-else>User 's status is undefined'</h1>
  </div>
</template>
