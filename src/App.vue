<script setup>
import Formulario from './components/Formulario.vue'
import Clima from './components/Clima.vue'
import Spinner from './components/Spinner.vue'
import useClima from './composables/useClima'
import Alerta from './components/Alerta.vue'
const {obtenerClima, clima, mostrarClima, cargando, error} = useClima()

</script>

<template>
  <h1 class="titulo">Buscador de Clima</h1>
  <div class="contenedor buscador-clima">
    <Formulario
    @obtener-clima="obtenerClima"
    ></Formulario>
    <Alerta v-if="error">{{ error }}</Alerta>
    <Spinner v-if="cargando"></Spinner>
    <Clima v-if="mostrarClima"
    :clima="clima"
    ></Clima>
    
  </div>
    
</template>

<style scoped>

</style>
