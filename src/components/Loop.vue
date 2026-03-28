<script setup>
import { ref } from 'vue'

const fruit = ref(['Apel', 'Jeruk', 'Mangga'])
</script>

<template>
  <ul>
    <li v-for="buah in fruit" :key="buah">{{ buah }}</li>
  </ul>
</template>
