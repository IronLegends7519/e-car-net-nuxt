<template>
<NuxtLink :to="`/car/${car.model}/${car.id}`">
    <article>
        <h2>{{car.marque}}</h2>
        <p>{{car.model}}</p>
    </article>
</NuxtLink>
</template>

<script>
export default {
  props: {
    car: Object
  }
}
</script>