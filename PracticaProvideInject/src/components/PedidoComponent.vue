<script setup>
  import { inject } from 'vue'

  const nombrePedido = inject('nombrePedido');

  const pedidoRealizado = () => {
    alert('Pedido realizado: ' + nombrePedido.value);
  };
</script>

<template>
  <h1>{{ nombrePedido }}</h1>
  <input type="text" v-model="nombrePedido" placeholder="Enter order name">
  <button @click="pedidoRealizado">Realizar pedido</button>
</template>

<style scoped>
/* Estilos opcionales */
</style>