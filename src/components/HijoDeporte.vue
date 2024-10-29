<template>
  <div>
    <li style="color: red">{{ nombredeporte }}</li>
    <button @click="seleccionarFavorito()">Seleccionar Favorito</button>
  </div>
</template>

<script>
export default {
  name: "HijoDeporte",
  props: ["nombredeporte"], //se añaden las props declaradas en el padre
  methods: {
    seleccionarFavorito() {
      console.log("Soy el hijo");
      //DEBEMOS REALIZAR LA LLAMADA AL PADRE
      //DICHA LLAMADA SE HACE MEDIANTE string "nombreMetodoParent"
      //PARA ENVIA INFORMACION, SE REALIZA CON COMAS POR CADA 
      //PARAMETRO QUE TENGAMOS EN LA RECEPCION
      this.$emit("seleccionarFavoritoParent", this.nombredeporte);
    },
  },
  mounted() {
    console.log(this.nombredeporte);
  },
};
</script>