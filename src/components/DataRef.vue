<!-- ref() ini bikin data jadi reactive,
 artinya kalu data berubah, UI yang punya data itu pun ikut 
 berubah otomatis -->
<script setup>
import { ref } from 'vue'

const name = ref('sauzan')

function gantiNama() {
  name.value = 'faza'
}
</script>

<template>
  <div>
    <h1>Halo nama saya {{ name }}</h1>
    <h2>Hai nama saya {{ name }}</h2>
    <button @click="gantiNama">Ganti Nama</button>
  </div>
</template>

<style lang="scss" scoped></style>
