<template>
    <USelectMenu
      searchable
      searchable-placeholder="Search for an option"
      class=" w-full lg:w-48"
      :placeholder="placeholder"
      :options="option"
      :modelValue="selected"
      @update:modelValue="updateSelected"
    />
  </template>
  
  <script>
  export default {
    props: {
      option: Array,
      placeholder: String,
      selected: String
    },
    methods: {
      updateSelected(value) {
        this.$emit('update:selected', value);
      }
    }
  }
  </script>