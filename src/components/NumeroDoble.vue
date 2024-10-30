<template>
  <div>
    <h1>Número doble Routes</h1>
    <button @click="redirectToHome">
        Go to Home
    </button>
    <h3 style="color: red">{{ mensaje }}</h3>
    <h5>Doble: {{ doble }}</h5>
  </div>
</template>

<script>
export default {
  name: "NumeroDoble",
  methods: {
    redirectToHome() {
        this.$router.push("/");
    }
  },
//   watch: {
//     "$route.params.numero"(nextVal, oldVal) {
//       //SOLAMENTE DEBEMOS REALIZAR LAS ACCIONES CUANDO NUESTRO PARAMETRO CAMBIE
//       if (nextVal != oldVal) {
//         this.mensaje = "Esto ha cambiado!!! " + this.$route.params.numero;
//         let valor = parseInt(this.$route.params.numero);
//         this.doble = valor * 2;
//       } 
//     },
//   },
  watch: {
    "$route.params.numero"(nextVal, oldVal) {
      // SOLAMENTE DEBEMOS REALIZAR LAS ACCIONES CUANDO NUESTRO PARAMETRO CAMBIE
      if (nextVal !== oldVal) {
        let paramNumero = nextVal;

        if (!paramNumero) {
          this.mensaje = "Sin parámetros en Routing";
          this.doble = 0; // Resetea el valor doble si no hay parámetro
        } else {
          this.mensaje = "Doble: " + paramNumero;
          let valor = parseInt(paramNumero);
          this.doble = valor * 2;
        }
      }
    },
  },
  data() {
    return {
      mensaje: "",
      doble: 0,
    };
  },
  mounted() {
    console.log("Param: " + this.$route.params.numero);
    //LOS PARAETROS SON STRING, NO IMPORTA SI SON NUMERICOS
    let paramNumero = this.$route.params.numero;
    if (paramNumero == "") {
      console.log("Sin parámetros");
      this.mensaje = "Sin parámetros en Routing";
    } else {
      console.log("Con parámetros");
      this.mensaje = "Parámetro reciido: " + paramNumero;
      let valor = parseInt(this.$route.params.numero);
      this.doble = valor * 2;
    }
  },
};
</script>