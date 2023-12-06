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
          placeholder="Qual Tarefa você deseja iniciar"
        />
      </div>
      <div class="column">
                <TemporizadorPlay />
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
  
});
</script>
