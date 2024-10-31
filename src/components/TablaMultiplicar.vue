<template>
  <div>
    <h1>Tabla de Multiplicar del {{ numero }}</h1>
    <button @click="redirectToHome">Go to Home</button>
    <br />
    <br />
    <table class="centered-table" border="1">
      <thead>
        <tr>
          <th>OPERACION</th>
          <th>RESULTADO</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="i in 10" :key="i">
          <td>{{ numero + " x " + i }}</td>
          <td>{{ numero * i }}</td>
        </tr>
      </tbody>
    </table>
    <hr />
  </div>
</template>

<script>
export default {
  name: "TablaMultiplicar",
  data() {
    return {
      numero: 0,
    };
  },
  methods: {
    redirectToHome() {
      this.$router.push("/");
    },
  },
  mounted() {
    console.log("Param: " + this.$route.params.numero);
    //LOS PARAETROS SON STRING, NO IMPORTA SI SON NUMERICOS
    let paramNumero = this.$route.params.numero;
    if (paramNumero == "") {
      console.log("Sin parámetros");
    } else {
      console.log("Con parámetros");
      let valor = parseInt(paramNumero);
      this.numero = valor;
    }
  },
  watch: {
    "$route.params.numero"(nextVal, oldVal) {
      // SOLAMENTE DEBEMOS REALIZAR LAS ACCIONES CUANDO NUESTRO PARAMETRO CAMBIE
      if (nextVal !== oldVal) {
        let paramNumero = nextVal;

        if (!paramNumero) {
          this.mensaje = "Sin parámetros en Routing";
          this.numero = 0; // Resetea el valor doble si no hay parámetro
        } else {
          this.mensaje = "Doble: " + paramNumero;
          let valor = parseInt(paramNumero);
          this.numero = valor;
        }
      }
    },
  },
};
</script>

<style>
.centered-table {
  margin-left: auto;
  margin-right: auto;
  border-collapse: collapse;
}
</style>
