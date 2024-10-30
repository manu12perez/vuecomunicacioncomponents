<template>
  <div>
    <ul id="menu">
      <li>
        <router-link to="/"> Home </router-link>|
      </li>
      <li>
        <router-link to="/padredeportes"> Deportes </router-link>|
      </li>
      <li>
        <router-link to="/padrenumeros"> Números </router-link>|
      </li>
      <li>
        <router-link to="/comics"> Comics </router-link>|
      </li>
      <li>
        <router-link to="/seleccionmultiple"> Selección Múltiple </router-link>|
      </li>
      <li>
        <router-link to="/sumacheckbox"> Suma Checkbox </router-link>|
      </li>
      <li>
        <router-link to="/numerodoble"> Número Doble SIN </router-link>|
      </li>
      <li v-for="numero in numeros" :key="numero">
        <router-link :to="'/numerodoble/' + numero"> Número Doble CON {{ numero }} </router-link>|
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "MenuComponent",
  data() {
    return{
        numeros: [15, 31, 56]
    }
  },
}
</script>

<style>
ul#menu li {
  display: inline;
}
</style>