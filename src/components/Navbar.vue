<template>
  <nav class="bg-slate-300 p-8 flex justify-between items-center">
    <div class="">
      <h1 class="text-slate-700 font-medium text-2xl">WebKu</h1>
    </div>
    <div class="py-2 px-6 rounded-xl bg-slate-50 shadow-2xl">
      <button @click="count++">click this: {{ count }}</button>
    </div>
  </nav>
</template>

<script setup>
import { ref } from 'vue'
const count = ref(0)
</script>

<style lang="scss" scoped></style>
