<template>
  <main class="columns is-gapless is multilane">
    <div class="columns is-one-quarter">
      <barraLateral />
    </div>

    <div class="column is-three-quarter">
      <FormularioComponents @aoSalvarTarefa="salvarTarefa"/>
      <div class="lista">
        <TarefaLista v-for="(tarefa, index) in tarefas" :key="index" :tarefa="tarefa"/>
       
      </div>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import barraLateral from "./components/barraLateral.vue";
import FormularioComponents from "./components/Formulario.vue";
import TarefaLista from "./components/TarefaLista.vue";
import ITarefa from "./interfaces/ITarefa";

export default defineComponent({
  name: "App",
  components: {
    barraLateral,
    FormularioComponents,
    TarefaLista,
  },
  data() {
    return {
      tarefas: [] as ITarefa[],
    };
  },
  methods: {
    salvarTarefa (tarefa: ITarefa) {
      this.tarefas.push(tarefa);
    }
  }
});
</script>

<style>
.lista {
  padding: 1.25rem;
}
</style>
