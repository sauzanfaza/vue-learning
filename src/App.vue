<script setup>
// import DataRef from './components/DataRef.vue'
// import BindingVue from './components/BindingVue.vue'
// import TwoWayBinding from './components/TwoWayBinding.vue'
// import Event from './components/Event.vue'
// import Loop from './components/Loop.vue'
import Navbar from './components/Navbar.vue'
import InputMhs from './components/InputMhs.vue'
import RenderingData from './components/RenderingData.vue'

import { ref } from 'vue'

const data = ref([
  { id: 1, name: 'Susan', semester: 7 },
  { id: 2, name: 'Puput', semester: 7 },
  { id: 3, name: 'Nuy', semester: 7 },
  { id: 4, name: 'Aura', semester: 7 },
])

function tambahMhs(mhsBaru) {
  const lastId = data.value.length > 0 ? data.value[data.value.length - 1].id : 0
  const newId = lastId + 1

  data.value.push({
    id: newId,
    ...mhsBaru,
  })
}
</script>

<template>
  <Navbar />
  <InputMhs @add-mhs="tambahMhs" />
  <RenderingData :data="data" />
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
