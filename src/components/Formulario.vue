<template>
  <div class="box">
    <div class="conlumns">
      <div
        class="column is-8"
        role="form"
        aria-label="Formuilário para criação de uma nova tarefa"
      >
        <input
          type="text"
          class="input"
          placeholder="Qual Tarefa você deseja iniciar" v-model="descricao"
        />
      </div>
      <div class="column">
                <TemporizadorPlay @aoTemporizadorFinalizado="finalizarTarefa" />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import TemporizadorPlay from './TemporizadorPlay.vue'

export default defineComponent({
  name: "FormularioContato",
  components: {
    TemporizadorPlay
  },
  data () {
    return {
      descricao: ''
    }
  },
  methods: {
    finalizarTarefa (tempoDecorrido: number) : void {
      console.log('Tempo da tarefa', tempoDecorrido);
      console.log('Descrição da tarefa', this.descricao);
      this.descricao = '';

    }
  }
  
});
</script>
