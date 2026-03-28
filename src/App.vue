<script setup>
import DataRef from './components/DataRef.vue'
import BindingVue from './components/BindingVue.vue'
import TwoWayBinding from './components/TwoWayBinding.vue'
import Event from './components/Event.vue'
import Loop from './components/Loop.vue'
</script>

<template>
  <h1>You did it!</h1>
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
  <Loop />
</template>

<style scoped></style>
