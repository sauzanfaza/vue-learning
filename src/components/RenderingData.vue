<template>
  <div class="border m-4 p-4">
    <h1>List Mahasiswa:</h1>
    <ul>
      <li v-for="mhs in data" :key="mhs.id">
        id: {{ mhs.id }}, nama: {{ mhs.name }}, semester: {{ mhs.semester }}
      </li>
    </ul>
  </div>
</template>

<script setup>
defineProps(['data'])
</script>

<style lang="scss" scoped></style>
