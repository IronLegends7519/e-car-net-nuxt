<template>
  <h1>profil</h1>
  <ul class="grid grid-cols-4 gap-10 mx-10">
    <li v-for="car in cars" :key="car.id">
      <afficheVoitureProfil :car="car" :name="carsId[0].name" />
    </li>
  </ul>
</template>
<script setup>

import  infoCar  from "../../infoCar.json"
import  profil  from "../../profil.json"
import  profil_InfoCar  from "../../profil_InfoCar.json"

const profils = ref({})
const cars = ref([])

profils.value = profil.map(p => p.id === 1)

const carsId = profil_InfoCar.filter(p => p.id === profils.value.id)

console.log(carsId)

cars.value = infoCar.filter(car => car.id === carsId[0].id_car)
</script>