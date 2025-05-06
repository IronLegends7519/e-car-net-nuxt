<template>
    <nuxt-link to="/profil">retour</nuxt-link>
    <div class="flex items-center justify-center gap-2 mt-5">
      <h2 class="text-4xl font-bold">{{cars.car.marque}}</h2>
      <p class="text-4xl">{{cars.car.model}}</p>
    </div>
    <div>
        <h2>reparation</h2>

        <p>{{cars.reparation.type}}</p>
    </div>
</template>

<script setup>
import tab from "../../infoCar.json"
    const route = useRoute();

const cars = ref({})

    tab.map(car => {
        if(car.id == route.params.id){
            cars.value = car
        }
    })

</script>