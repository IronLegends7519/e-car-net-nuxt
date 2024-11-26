<script setup>
    import afficheVoiture from "../components/afficheVoiture.vue"
    import Filter from "../components/Filter.vue"
    let tab = [{id:1, marque:"audi", modele:"A3"}, {id:2, marque:"bmw", modele:"serie 3"}]
    let marque = ref([])
    let model = ref([])

    marque.value = tab.map(car => car.marque)
    model.value = tab.map(car => car.modele)


</script>

<template>
    <h1>bonjour utilisateur</h1>
    <nav>
        <ul>
            <li><nuxt-link to="/">Accueil</nuxt-link></li>
            <li><nuxt-link to="/profil">votre profil</nuxt-link></li>
        </ul>
    </nav>
    <ul>
        <li>
            <Filter :option="marque" :placeholder='"choice a marque"'  />
        </li>
        <li>
            <Filter :option="model" :placeholder='"choice a model"'  />
        </li>
    </ul>
    <section v-for="car in tab" :key="car.id">
        <afficheVoiture :car="car" />
    </section>
</template>
