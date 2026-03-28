<script setup>
import { ref } from 'vue'

const isLogin = ref(true)
</script>

<template>
  <p v-if="isLogin">Welcome</p>
  <p v-else>Silahkan Login</p>
</template>
