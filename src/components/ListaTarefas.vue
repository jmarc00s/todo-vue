<template>
  <div class="lista-tarefas row">
      <tarefa 
            class="col-md" 
            v-for="tarefa in tarefas" 
            :key="tarefa.descricao" 
            :tarefa="tarefa"
            v-on:remover-tarefa="removerTarefa($event)" />
  </div>
</template>

<script>
import Tarefa from './Tarefa';
export default {
    components: {
        Tarefa
    },
    props: {
        tarefas: Array
    },

    methods: {
        removerTarefa(tarefa) {
            if(!tarefa) return;

            this.tarefas.splice(this.tarefas.indexOf(tarefa), 1);
        }
    }, 

    data() {
        return {

        }
    }

}
</script>

<style>
.lista-tarefas {

}
</style>