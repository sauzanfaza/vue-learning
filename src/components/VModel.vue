<script setup>
import { ref } from 'vue'

const text = ref('')
</script>

<template>
  <!-- tanpa v-model -->
  <input :value="text" @input="(e) => (text = e.target.value)" />

  <!-- dengan v-model -->
  <input v-model="text" />
</template>
