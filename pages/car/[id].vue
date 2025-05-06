<template>
    <div class="flex items-center justify-center gap-2 mt-5">
          <h2 class="text-4xl font-bold">{{cars.marque}}</h2>
          <p class="text-4xl">{{cars.model}}</p>
        </div>
</template>

<script setup>
import tab from "../../car.json"
    const route = useRoute();

const cars = ref({})

    tab.map(car => {
        if(car.id == route.params.id){
            cars.value = car
        }
    })

</script>