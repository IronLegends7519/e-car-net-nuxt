<script setup>
    const selected = ref("")
</script>

<template>
    <USelectMenu
    searchable
    searchable-placeholder="Search for an option"
    class="w-full lg:w-48"
    :placeholder="placeholder"
    :options="option"
    v-model="selected"
  />
</template>
<script>
    export default {
        props: {
            option: Array,
            placeholder: String
        }
    }
</script>
