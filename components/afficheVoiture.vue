<template>
<NuxtLink :to="`/car/${car.id}`" class = "flex flex-col justify-center bg-gray-200 p-4 rounded-lg shadow-md hover:shadow-lg transition-shadow duration-300">
        <img :src="car.image ? `/_nuxt/assets/${car.image}` : '/_nuxt/assets/Img.png'" alt="car image" class="w-full h-40 object-cover rounded-lg mb-2" />
        <div class="flex flex-col gap-2">
          <h2 class="text-4xl font-bold">{{car.marque}}</h2>
          <p class="text-4xl">{{car.model}}</p>
          <p class="text-xl">{{ car.year }}</p>
        </div>
</NuxtLink>
</template>

<script>
export default {
  props: {
    car: Object
  }
}
</script>