<template>
  <div>
    <ul id="menuTabla">
      <li><router-link to="/"> Home </router-link>|</li>
      <li><router-link to="/tablamultiplicar"> Tabla sin Param </router-link>|</li>
      <li v-for="num in numeros" :key="num">
        <router-link :to="'/tablamultiplicar/' + num">
          Tabla Multiplicar {{ num }}</router-link
        >|
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "MenuTablaMultiplicar",
  data() {
    return {
      numeros: [],
    };
  },
  methods: {
    generarNum() {
      while (this.numeros.length < 5) {
        let numeroAleatorio = Math.floor(Math.random() * 100) + 1; 
        if (!this.numeros.includes(numeroAleatorio)) { // Asegura que el número no esté repetido
          this.numeros.push(numeroAleatorio);
        }
      }
    },
  },
  mounted() {
    this.generarNum(); // Llama al método al montar el componente
  },
};
</script>

<style>
ul#menuTabla li {
  display: inline;
}
</style>