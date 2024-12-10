<script setup>
  import { inject } from 'vue'

  const moneda = inject('moneda');
</script>

<template>
  <label for="moneda">Seleccionar moneda:</label>
  <select id="moneda" v-model="moneda">
    <option value="EUR">Euros (€)</option>
    <option value="USD">Dólares ($)</option>
  </select>
</template>

<style scoped>

</style>