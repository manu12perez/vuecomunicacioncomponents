<template>
  <div>
    <li style="color:blue">Número hijo: {{ dibujonumero }}</li>
    <button @click="resultado()">Calcular</button>
  </div>
</template>

<script>
export default {
  name: "HijoNumero",
  props: ["dibujonumero"],
  methods: {
    resultado() {
      console.log("Soy el hijo");
      this.$emit("sumarNumeros", this.dibujonumero)
    }
  },
  mounted() {
    console.log(this.dibujonumero);
  },
};
</script>