<script setup>
import afficheVoiture from "../components/afficheVoiture.vue"
import Filter from "../components/Filter.vue"
import { ref, watch } from "vue"
import tab from "../car.json"

const marque = ref([])
const model = ref([])

const uniqueMarque = [...new Set(tab.map(car => car.marque))]
const uniqueModel = [...new Set(tab.map(car => car.model))]

marque.value = ["All", ...uniqueMarque]
model.value = ["All", ...uniqueModel]

const selectedMarque = ref("All")
const selectedModel = ref("All")

const filteredCars = ref(tab)

const filter = () => {
  if (selectedMarque.value === "All" && selectedModel.value === "All") {
    return tab
  }
  if (selectedMarque.value === "All") {
    return tab.filter(car => car.model === selectedModel.value)
  }
  if (selectedModel.value === "All") {
    return tab.filter(car => car.marque === selectedMarque.value)
  }
  return tab.filter(car => car.marque === selectedMarque.value && car.model === selectedModel.value)
}

const update = () => {
  filteredCars.value = filter()
}

watch([selectedMarque, selectedModel], () => {
  update()
})
</script>

<template>

  <div class="flex flex-col gap-10">
    <ul class="flex gap-4 items-center justify-center mt-4">
      <li>
        <Filter :option="marque" :placeholder="'choice a marque'" :selected="selectedMarque" @update:selected="selectedMarque = $event" />
      </li>
      <li>
        <Filter :option="model" :placeholder="'choice a model'" :selected="selectedModel" @update:selected="selectedModel = $event" />
      </li>
    </ul>
    <ul class="grid grid-cols-4 gap-10 mx-10">
      <li v-for="car in filteredCars" :key="car.id">
        <afficheVoiture :car="car" />
      </li>
    </ul>
  </div>

</template>