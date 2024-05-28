<script setup>
import { ref } from 'vue';

  const nombre = "Lilia";
  const apellido = "Soto Llamas";

  const styleColor = "color: green;"
  const claseExtra = "big"

  const existe = true;

  const palabras = ["Harry", "Louis", "Zayn"];
  const counter = ref(0);
  const num1 = ref(0);
  const number = ref(0);

  const venta = [
    {
      producto: 'Celular',
      precio: 20,
      stock: 5
    },
    {
      producto: 'Tablet',
      precio: 40,
      stock: 0
    },
    {
      producto: 'Computadora',
      precio: 200,
      stock: 10
    }
  ]

  const mostrarMensaje = () => {
    alert("Me cliqueaste!😒");
  }


  let increment = () => {
    counter.value++;
  }

  let decrement = () => {
    counter.value--;
  }

  let agregar = () => {
    number.value = num1.value;
  }

</script>

<template>
  <h1>{{ nombre }}</h1>
  <p>{{ apellido }}</p>
  <p :class="claseExtra" :style="styleColor">Hola</p>

  <h1 v-if="!existe">Hola aquí</h1>
  <h1 v-else="">Else aquí</h1>
  
  <ul>
    <li v-for="palabra in palabras">{{ palabra }}</li>
  </ul>

  <!-- FOR AND IF -->
  <ul>
    <template v-for="item in venta">
      <li v-if="item.stock > 0">
        {{ item.producto }} - {{ item.precio }}
      </li>
    </template>
  </ul>

  <button @click="mostrarMensaje">Click me!</button>
  <button @click="increment">Sumar</button>
  <button @click="decrement">Decrementa</button>
  <br>
  <p>{{ counter }}</p>
  <input type="number" v-model="num1">
  <button @click="agregar">Agregar</button>
  <p>{{ number }}</p>

</template>

<style>
  h1{
    color: rgb(255, 148, 201);
  }
</style>