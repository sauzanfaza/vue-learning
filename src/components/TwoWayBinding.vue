<!-- binding two way -->
<template>
  <div>
    <input v-model="inputText" />
    <p>{{ inputText }}</p>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const inputText = ref('')
</script>

<style lang="scss" scoped></style>
