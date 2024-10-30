<template>
  <div>
    <h1 style="color: red">Números Padre</h1>
    <h3 style="background-color: yellow" v-if="resultado">
      La suma es: {{ resultado }}
    </h3>
    <button @click="generarNum()">Generar Número Aleatorio</button>

    <hr />
    <ul v-for="num in numeros" :key="num">
      <HijoNumero :dibujonumero="num" v-on:sumarNumeros="sumarNumeros" />
    </ul>
    <hr />
  </div>
</template>

<script>
import HijoNumero from "./HijoNumero.vue";

export default {
  name: "PadreNumeros",
  components: {
    HijoNumero,
  },
  methods: {
    generarNum() {
      let numeroAleatorio = parseInt(Math.floor(Math.random() * 100) + 1);
      this.numeros.push(numeroAleatorio);
    },
    
    sumarNumeros(numSuma) {
      console.log("Yo soy el padre");
      this.resultado += numSuma;
    },
  },
  data() {
    return {
      numeros: [],
      resultado: null,
    };
  },
};
</script>