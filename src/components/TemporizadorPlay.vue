<template>
     <div
          class="is-flex is-align-items-center is-justify-content-space-between"
        >   </div>
        <cronometroContador :tempoEmSegundos="tempoEmSegundos"/>
     
        <button class="button" @click="inciar">
          <span class="icon">
            <i class="fas fa-play"></i>
          </span>
          <span>play</span>
        </button>

        <button class="button" @click="finalizar">
          <span class="icon">
            <i class="fas fa-stop"></i>
          </span>
          <span>Finalizando</span>
        </button>
   
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import cronometroContador from './cronometroContador.vue'

export default defineComponent({
    name: "TemporizadorPlay",
    components: {
        cronometroContador
    },
data() {
    return {
      tempoEmSegundos: 0,
      cronometroContador: 0

    };
  },

  methods: {
    inciar() {
      this.cronometroContador = setInterval(() => {
      this.tempoEmSegundos += 1
      }, 1000);
    
    },
    finalizar() {
    clearInterval(this.cronometroContador);
  },
},
})
</script>
