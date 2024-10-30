<template>
  <div>
    <h1>Suma Checkbox</h1>
    <button @click="generarCheckbox">Generar Checkbox</button>
    <div class="checkbox-container">
      <div v-for="checkbox in checkboxes" :key="checkbox" class="checkbox-item">
        <input
          type="checkbox"
          :value="checkbox"
          v-model="selectedCheckboxes"
          @change="calcularSuma"
        />
        {{ checkbox }}
      </div>
    </div>
    <h2 style="color: blue">La suma seleccionada es: {{ suma }}</h2>
  </div>
</template>

<script>
export default {
  name: "SumaCheckbox",
  data() {
    return {
      checkboxes: [],
      selectedCheckboxes: [],
      suma: 0,
    };
  },
  methods: {
    generarCheckbox() {
      let numeroAleatorio = Math.floor(Math.random() * 100) + 1;
      this.checkboxes.push(numeroAleatorio);
    },
    calcularSuma() {
      this.suma = this.selectedCheckboxes.reduce((acc, val) => acc + Number(val), 0);
    },
  },
};
</script>

<style>
.checkbox-container {
  display: flex;
  flex-wrap: wrap; /* Para permitir que se muevan a la siguiente línea si hay muchos */
}

.checkbox-item {
  margin-right: 10px; /* Espacio entre los checkboxes */
}
</style>
