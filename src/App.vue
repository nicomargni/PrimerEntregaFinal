<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <!-- $props $refs -->
    <HelloWorld :msg="usuario"/>
    <!-- $emit --> 
    <Padre-Prueba />
    <!-- slots -->
    <slot-prueba>
      <h3>Osito mediante slot</h3>
      <img src="https://i.pinimg.com/550x/56/ae/09/56ae095cd445ada49001caad87ba136e.jpg" style="width: 200px; height:200px">
      <p slot="precio">${{precio}}</p>
    </slot-prueba>
    <!-- Filtros -->
    <filtros-prueba/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import PadrePrueba from './components/PadrePrueba.vue'
import SlotPrueba from './components/SlotPrueba.vue'
import FiltrosPrueba from './components/FiltrosPrueba.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    PadrePrueba,
    SlotPrueba,
    FiltrosPrueba
  },
  data(){
    return{
    usuario:{nombre:"Jose Luis Anakatashe", edad:34},
    precio:2399
    }

  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
