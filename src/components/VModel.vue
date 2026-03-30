<!-- binding: cara menghubungkan data (di script)
 dengan tampilan (di template) (proses mengirim data dari logic ke tampilan) 
 data di JavaScript bisa muncul di HTML karena ada binding-->

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
