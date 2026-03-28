<!-- Binding: cara ngirim data dari script ke template
 ada 3 jenis utama binding -->

<!-- 1. {{ name }} -->
<!-- 2. v-bind/: -->
<script setup>
import { ref } from 'vue'

const link = ref('https://vuejs.org')
</script>

<template>
  <a :href="link">Klik link ini yaa</a>
</template>
