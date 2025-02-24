<script setup lang="ts">
import { isVoidExpression } from 'typescript'
import { ref } from 'vue'

const name = ref('')

const imgUrl = ref('https://masteringjs.io/assets/images/vue/vue.png')
const altContent = ref('this is vuejs logo')
const score = Math.floor(Math.random() * 10)

const isVisible = ''
const dynamicAttr = ref('href')
const link = ref('https://vuejs.org')

// truly and falsy
</script>

<template>
  <div>
    <!-- v-bind -->
    <img v-bind:src="imgUrl" :alt="altContent" />

    <!-- two way binding - v-model -->
    <input v-model="name" placeholder="Nhập tên của bạn" />
    <p>Xin chào, {{ name }}</p>

    <!-- v-if, v-else-if, v-else -->
    <h1 v-if="score < 4">F</h1>
    <h1 v-else-if="score < 8">B</h1>
    <h1 v-else>A</h1>

    <!-- v-show -->
    <h1 v-show="isVisible">Hello anh em</h1>

    <!-- Dùng Dynamic Argument với v-bind để bind thuộc tính động -->
    <a :[dynamicAttr]="link" style="text-decoration: none">Nhấn vào đây</a>
  </div>
</template>
