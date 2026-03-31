<script setup>
// import DataRef from './components/DataRef.vue'
// import BindingVue from './components/BindingVue.vue'
// import TwoWayBinding from './components/TwoWayBinding.vue'
// import Event from './components/Event.vue'
// import Loop from './components/Loop.vue'
import Navbar from './components/Navbar.vue'
import InputMhs from './components/InputMhs.vue'
import RenderingData from './components/RenderingData.vue'
import SearchBar from './components/SearchBar.vue'

import { ref, computed, onMounted, watch } from 'vue'

const search = ref('')

const data = ref([
  { id: 1, name: 'Susan', semester: 7 },
  { id: 2, name: 'Chanyeol', semester: 7 },
  { id: 3, name: 'Kai', semester: 7 },
  { id: 4, name: 'Sehun', semester: 7 },
])

// onMounted(() => {
//   data.value = [
//     { id: 1, name: 'Susan', semester: 7 },
//     { id: 2, name: 'Chanyeol', semester: 7 },
//     { id: 3, name: 'Kai', semester: 7 },
//     { id: 4, name: 'Sehun', semester: 7 },
//   ]
// })
// onMounted itu mirip useEffect() tapi klo onMouonted cuman sekali doang, dia dipakai buat jalan sekali saat component muncul
// biasanya buat fetch API
// onMounted(() => {
//   fetchData()
// }, [])

//onMounted simpelnya = pas pertama kali buka halaman, jalanin ini

// perlu diingat sannn!!!
// ref --> buat simpen data
//onMounted --> buat waktu jalanin logic
// computed --> buat olah data

// watch = useEffect() alias ngereaksiin perubahan
// bentuk dasar: watch(apa_yang_dipantau, callback)

const filteredData = computed(() => {
  return data.value.filter((mhs) => mhs.name.toLowerCase().includes(search.value.toLowerCase()))
})

function tambahMhs(mhsBaru) {
  const lastId = data.value.length > 0 ? data.value[data.value.length - 1].id : 0
  const newId = lastId + 1

  data.value.push({
    id: newId,
    ...mhsBaru,
  })
}

function handleSearch(val) {
  search.value = val
  watch(search, (val) => {
    console.log('susan lagi search: ', val) //liat di console tiap huruf yang di ketik di search bar di watch sama fungsi watch wkwk
  })
  //watch ini buat jalanin efek tambahan biasanya, dan dia gak return value
}
</script>

<template>
  <Navbar />
  <InputMhs @add-mhs="tambahMhs" />
  <SearchBar @update-search="handleSearch" />
  <RenderingData :data="filteredData" />
  <!-- <h1>You did it!</h1>
  <p>
    Visit <a href="https://vuejs.org/" target="_blank" rel="noopener">vuejs.org</a> to read the
    documentation
  </p>
  <p>Halo ini aplikasi vue pertama saya setelah sekian lama heheh</p>
  <DataRef />
  <BindingVue />
  <TwoWayBinding />
  <Event />
  <h1>Daftar buah:</h1>
  <Loop /> -->
</template>

<style scoped></style>
