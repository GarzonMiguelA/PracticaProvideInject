<script setup>
  import { ref, provide } from 'vue'
  import Pedido from '@/components/CurrencyComponent.vue'
  import Currency from '@/components/PedidoComponent.vue'
  
  const productos = [       
    { name: "Hamburger 🍔", price: 5 },
    { name: "Cheeseburger 🧀", price: 6 },
    { name: "Impossible Burger 🥕", price: 7 },
    { name: "Fries 🍟", price: 2 }
  ]

  const nombrePedido = ref('');
  const productosComprados = ref([]);
  const moneda = ref('EUR'); 

  provide('nombrePedido', nombrePedido);
  provide('moneda', moneda);
  provide('productosComprados', productosComprados);

  const agregarProducto = (producto) => {
    productosComprados.value.push(producto);
    const productosNombres = productosComprados.value.map(p => p.name).join(', ');
    alert(`Productos en el carrito: ${productosNombres}`);
  };

  const pedidoRealizado = () => {
    alert('Pedido realizado: ' + nombrePedido.value);
  };
</script>

<template>
  <Pedido />
  <Currency />
  <div v-for="producto in productos" :key="producto.name">
    <span> {{ producto.name }} - {{ moneda === 'EUR' ? '€' : '$' }} {{ producto.price }}</span>
    <button @click="() => agregarProducto(producto)"> Añadir al carrito </button>
  </div>
</template>

<style scoped>

</style>