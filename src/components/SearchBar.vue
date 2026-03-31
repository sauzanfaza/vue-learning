<!-- Mempelajari computed dengan filter di searchbar -->
<template>
  <div class="flex">
    <input
      type="text"
      placeholder="input text"
      v-model="search"
      @input="searchBar"
      class="flex border m-4 py-2 px-4 rounded-2xl"
    />
    <button
      @click="searchBar"
      class="bg-green-500 py-2 px-4 m-4 rounded-2xl hover:bg-green-600 cursor-pointer"
    >
      search
    </button>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const search = ref('')
const emit = defineEmits(['update-search'])

function searchBar() {
  emit('update-search', search.value)
}
</script>

<style lang="scss" scoped></style>

<!-- SearchBar (emit keyword)
        ↓
App.vue (simpan search)
        ↓
computed (filter data)
        ↓
RenderingData (tampil hasil) -->

<!-- computed: data turunan otomatis dari state utama
 gampangnya: data yang dihitung dari data lain, dan bakal 
 update sendiri kalo sumbernya berubah
 
 Flownya:
 data berubah
atau
search berubah
        ↓
computed jalan otomatis
        ↓
UI ikut update
-->
