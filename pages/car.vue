<template>
    <h1>voici la {{ cars.marque }} {{ cars.model }}</h1>
</template>

<script setup>
import tab from "../car.json"
    const route = useRoute();
definePageMeta({
  path: "/car/:model/:id(\\d+)",
});

const cars = ref({})

    tab.map(car => {
        if(car.id == route.params.id){
            cars.value = car
        }
    })
</script>