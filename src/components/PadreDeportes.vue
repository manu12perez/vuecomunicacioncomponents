<template>
  <div>
    <h1 style="color: blue">Padre Deportes</h1>
    <h2 style="background-color:yellow" v-if="favorito">
        Su deporte favorito es: {{ favorito }}
    </h2>
    <ul v-for="sport in deportes" :key="sport">
      <!-- :nombredeporte es el props, se le añaden los ":" porque va a ser una variable (dinámica), si fuera un texto estático no se ponen ":" -->
      <HijoDeporte :nombredeporte="sport"
        v-on:seleccionarFavoritoParent="seleccionarFavoritoParent" />
    </ul>
  </div>
</template>

<script>
import HijoDeporte from "./HijoDeporte.vue";

export default {
  name: "PadreDeportes",
  components: {
    HijoDeporte,
  },
  methods: {
    //CREAMOS UN METODO PARA QUE SEA LLAMADO DESDE EL HIJO
    seleccionarFavoritoParent(deporteFavorito) {
      console.log("Yo soy tu padre");
      this.favorito = deporteFavorito;
    },
  },
  data() {
    return {
      deportes: ["Futbol", "Surf", "Snowboard", "Tenis", "Padel", "Basket"],
      favorito: null,
    };
  },
};
</script>