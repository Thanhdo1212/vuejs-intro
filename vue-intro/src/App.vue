<script setup lang="ts">
import { ref, watch } from 'vue'

const question = ref('')
const answer = ref('Questions usually contain a question mark. ;-)')
const loading = ref(false)

// Theo dõi sự thay đổi của question
watch(question, async (newQuestion) => {
  if (newQuestion.includes('?')) {
    loading.value = true
    answer.value = 'Thinking...'
    try {
      const res = await fetch('https://yesno.wtf/api')
      answer.value = (await res.json()).answer
    } catch (error) {
      answer.value = 'Error! Could not reach the API. ' + error
    } finally {
      loading.value = false
    }
  }
})
</script>

<template>
  <p>
    Hỏi một câu hỏi có thể trả lời bằng "có" hoặc "không":
    <input v-model="question" :disabled="loading" />
  </p>
  <p>{{ answer }}</p>
</template>
