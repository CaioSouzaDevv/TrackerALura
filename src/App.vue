<template>
  <main class="columns is-gapless is multilane">
    <div class="columns is-one-quarter">
      <barraLateral />
    </div>

    <div class="column is-three-quarter">
      <FormularioComponents />
    <div class="lista">
      <TarefaLista /> 
       <TarefaLista /> 
        <TarefaLista /> 
    </div>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import barraLateral from "./components/barraLateral.vue";
import FormularioComponents from "./components/Formulario.vue";
import TarefaLista from "./components/TarefaLista.vue";
export default defineComponent({
  name: "App",
  components: {
    barraLateral,
    FormularioComponents,
    TarefaLista
  },
});
</script>

<style>
.lista {
  padding: 1.25rem;
  
}
</style>
