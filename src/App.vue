<template>
  <h1>Prueba Esteban</h1>
  <img alt="Vue logo" src="./assets/logo.png">
  <!-- 3)Llamar el componente, lo puedes llamar las veces que se necesite -->
  <Counter/>


</template>

<script>
// 1) importar componente
import Counter from '@/components/counter.vue'



export default {

  name: 'App',
    // 2)Agregar el componente
  components: { Counter }


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
