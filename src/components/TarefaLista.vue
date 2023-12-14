<template>
  <BoxTemplate class="box has-text-weight-bold">
    <div class="columns">
      <div class="column is-7">
        {{ tarefa.descricao }}
      </div>
      <div class="column">
        <cronometroContador :tempoEmSegundos="tarefa.duracaoEmSegundos" />
      </div>
    </div>
  </BoxTemplate>
</template>

<script lang="ts">
import { defineComponent, PropType } from "vue";
import cronometroContador from "./cronometroContador.vue";
import ITarefa from "../interfaces/ITarefa";
import BoxTemplate from "./Box.vue";

export default defineComponent({
  name: "TarefaLista",
  components: {
    cronometroContador,
    BoxTemplate,
  },
  props: {
    tarefa: {
      type: Object as PropType<ITarefa>,
      required: true,
    },
  },
});
</script>

