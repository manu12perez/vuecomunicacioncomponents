<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <h1>Título Estatático</h1>
  <MenuComponent />
  <br/>
  <hr />
  <MenuTablaMultiplicar />
  <hr />
  <router-view />
  <hr />
</template>

<script>
// // import HelloWorld from './components/HelloWorld.vue'
import MenuComponent from './components/MenuComponent.vue'
import MenuTablaMultiplicar from './components/MenuTablaMultiplicar.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld
    MenuComponent,
    MenuTablaMultiplicar
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
