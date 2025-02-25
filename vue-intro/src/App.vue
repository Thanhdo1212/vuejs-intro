<script setup lang="ts">
import { ref } from 'vue'

const checkedNames = ref([])
const gender = ref('')
const color = ref('')
</script>

<template>
  <h1>ALL THE NAME : {{ checkedNames }}</h1>
  <input
    id="thanh"
    type="checkbox"
    v-model="checkedNames"
    style="width: 50px; height: 50px"
    value="THANH"
  />
  <label for="thanh">Thanh</label>
  <input
    id="do"
    type="checkbox"
    v-model="checkedNames"
    style="width: 50px; height: 50px"
    value="DO"
  />
  <label for="do">Do</label>
  <input
    id="duc"
    type="checkbox"
    v-model="checkedNames"
    style="width: 50px; height: 50px"
    value="DUC"
  />
  <label for="duc">Duc</label>

  <!-- ratio check with v-model-->

  <h1>Ratio box</h1>
  <h2>Gender : {{ gender }}</h2>

  <input id="male" type="radio" v-model="gender" style="width: 50px; height: 50px" value="male" />
  <label for="male">MALE</label>
  <input
    id="female"
    type="radio"
    v-model="gender"
    style="width: 50px; height: 50px"
    value="female"
  />
  <label for="female">FEMALE</label>

  <!-- selected with v-model-->

  <h1>SELECT</h1>
  <h2>Your favorite color : {{ color }}</h2>
  <select v-model="color">
    <option value="" disabled>Please select one</option>
    <option value="red">RED</option>
    <option value="blue">BLUE</option>
    <option value="green">GREEN</option>
  </select>
</template>
