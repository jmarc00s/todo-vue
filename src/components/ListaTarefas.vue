<template>
  <div class="lista-tarefas row">
      <tarefa class="col-md" v-for="tarefa in tarefas" :key="tarefa.descricao" :tarefa="tarefa" />
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