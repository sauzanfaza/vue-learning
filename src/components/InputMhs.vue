<template>
  <div class="flex flex-col border p-8 m-4">
    <input type="text" placeholder="Name" class="border mb-4 p-4 rounded-2xl" v-model="name" />
    <input type="text" placeholder="Semester" class="border p-4 rounded-2xl" v-model="semester" />
    <button
      @click="kirimData"
      class="mt-4 p-4 border bg-green-600 hover:bg-green-700 rounded-2xl cursor-pointer"
    >
      submit
    </button>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const name = ref('')
const semester = ref('')

// define emit
const emit = defineEmits(['add-mhs']) //daftarin dulu event nya, dengan nama 'add-mhs'
// child itu gak bisa langsung ubah data parent
// jadi dia harus ngomong dulu ke parent lewat event, nah itu disebut emit

//fungsi kirimdata
function kirimData() {
  emit('add-mhs', {
    //kirim event + data, nnti parent nangkep dengan <InputMhs @add-mhs="tambahMhs /> di App.vue"
    name: name.value,
    semester: semester.value,
  })

  name.value = ''
  semester.value = ''
}
</script>

<style lang="scss" scoped></style>
