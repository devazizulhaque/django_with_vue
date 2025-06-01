<script setup>
import { onMounted, ref } from 'vue'
import api from '../services/api'

const message = ref('Loading...')

onMounted(async () => {
  const res = await api.get('/hello/')
  message.value = res.data.message
})
</script>

<template>
  <h1>{{ message }}</h1>
</template>
