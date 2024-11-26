<template>
<a href="car-car.modele">
    <article>
        <h2>{{car.marque}}</h2>
        <p>{{car.modele}}</p>
    </article>
</a>
</template>

<script>
export default {
  props: {
    car: Object
  },
  mounted() {
    console.log(this.car);
  }
}
</script>