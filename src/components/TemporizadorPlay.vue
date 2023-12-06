<template>
  <div
    class="is-flex is-align-items-center is-justify-content-space-between"
  ></div>
  <cronometroContador :tempoEmSegundos="tempoEmSegundos" />

  <button class="button" @click="inciar" :disabled="cronometroRodando">
    <span class="icon">
      <i class="fas fa-play"></i>
    </span>
    <span>play</span>
  </button>

  <button class="button" @click="finalizar" :disabled="!cronometroRodando">
    <span class="icon">
      <i class="fas fa-stop"></i>
    </span>
    <span>Finalizando</span>
  </button>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import cronometroContador from "./cronometroContador.vue";

export default defineComponent({
  name: "TemporizadorPlay",
  components: {
    cronometroContador,
  
  },
  data() {
    return {
      tempoEmSegundos: 0,
      cronometroContador: 0,
        cronometroRodando: false
    };
  },

  methods: {
    inciar() {
        this.cronometroRodando = true;
      this.cronometroContador = setInterval(() => {
        this.tempoEmSegundos += 1;
      }, 1000);
    },
    finalizar() {
        this.cronometroRodando = false;
      clearInterval(this.cronometroContador);
    },
  },
});
</script>
