<template>
    <div class="box has-text-weight-bold">
        <div class="columns">
            <div class="column is-7">
                Descrição da tarefa
            </div>
            <div class="column">
                <cronometroContador :tempoEmSegundos="15"/>
            </div>
        </div>

    </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import cronometroContador from "./cronometroContador.vue";


export default defineComponent({
name: 'TarefaLista',
components: {
    cronometroContador
}
})
</script>
<style scoped>
.box {
    background: #faf0ca;
}
</style>
