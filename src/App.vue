<template>
  <main
    class="columns is-gapless is multilane"
    :class="{ 'modo-escuro': modoEscuroAtivo }"
  >
    <div class="columns is-one-quarter">
      <barraLateral @aoTemaAlterado="trocarTema" />
    </div>

    <div class="column is-three-quarter conteudo">
      <FormularioComponents @aoSalvarTarefa="salvarTarefa" />
      <div class="lista">
        <TarefaLista
          v-for="(tarefa, index) in tarefas"
          :key="index"
          :tarefa="tarefa"
        />
      </div>
      <BoxTemplate v-if="listaEstaVazia">
        Você não está muito produtivo hoje :(
      </BoxTemplate>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import barraLateral from "./components/barraLateral.vue";
import FormularioComponents from "./components/Formulario.vue";
import TarefaLista from "./components/TarefaLista.vue";
import ITarefa from "./interfaces/ITarefa";
import BoxTemplate from "./components/Box.vue";

export default defineComponent({
  name: "App",
  components: {
    barraLateral,
    FormularioComponents,
    TarefaLista,
    BoxTemplate,
  },
  data() {
    return {
      tarefas: [] as ITarefa[],
      modoEscuroAtivo: false,
    };
  },
  computed: {
    listaEstaVazia(): boolean {
      return this.tarefas.length === 0;
    },
  },
  methods: {
    salvarTarefa(tarefa: ITarefa) {
      this.tarefas.push(tarefa);
    },
    trocarTema(modoEscuroAtivo: boolean) {
      this.modoEscuroAtivo = modoEscuroAtivo;
    },
  },
});
</script>

<style>
main {
  --bg-primary: #fff;
  --text-primary: #000;
}
main.modo-escuro {
  --bg-primary: #2b2d42;
  --text-primary: #ddd;
}
.conteudo {
  background-color: var(--bg-primary);
}
</style>
