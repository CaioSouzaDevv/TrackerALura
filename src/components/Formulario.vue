<template>
  <div class="box formulario">
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
  emits: ['aoSalvarTarefa'],
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
      this.$emit('aoSalvarTarefa', {
        duracaoEmSegundos: tempoDecorrido,
        descricao: this.descricao
      })
      this.descricao = '';

    }
  }
  
});
</script>
<style>
.formulario {
  color: var(--text-primary);
  background-color: var(--bg-primary) ;
  }
</style>
