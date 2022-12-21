<template>
  <div>
    <button @click="noReservados">Mostrar No Reservados</button>
  </div>
</template>

<script setup>
import { ref } from "vue";
import axios from "axios";

const sinReservar = ref([]);
const noReservados = async () => {
  try {
    const respuesta = await axios.get(
      `http://localhost:3000/materiales?RESERVADO=No`
    );
    sinReservar.value = respuesta.data;
    console.log(sinReservar.value);
  } catch (e) {
    console.log(e);
  }
};
</script>

<style lang="scss" scoped>
button {
  border-radius: 2px;
  border-color: black;
}
</style>
