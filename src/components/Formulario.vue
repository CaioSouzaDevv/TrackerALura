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
        <div
          class="is-flex is-align-items-center is-justify-content-space-between"
        >
          <section>
            <strong>{{ tempoDecorrido }}  </strong>
        </section>
        </div>
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
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "FormularioContato",
  data() {
    return {
      tempoEmSegundos: 0,
    };
  },
  computed: {
tempoDecorrido () : string{
    return new Date(this.tempoEmSegundos * 1000).toISOString().substr(11,8)
}
  },
  methods: {
    inciar() {
      setInterval(() => {
      this.tempoEmSegundos += 1
      }, 1000);
      console.log("iniciando");
    },
    finalizar() {
      console.log("Finalizando");
    },
  },
});
</script>
