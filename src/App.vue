<template>
  <div id="app">
   <task-input v-on:tarefa-adicionada="adicionarTarefa($event)"/>
   <lista-tarefas :tarefas="tarefas" />
   
  </div>
</template>

<script>

import TaskInput from './components/TarefaInput';
import ListaTarefas from './components/ListaTarefas';

export default {
  components: {
    TaskInput,
    ListaTarefas
  },
  methods: {
    adicionarTarefa(tarefa){
      this.tarefas.push(tarefa);
    }
  },
  data() {
    return {
      tarefas: []
    }
  }
}
 
</script>

<style>
#app {
  display: flex;
  flex-direction: column;
  align-items: center;
  align-content: center;  
  flex: 1 0 auto;
  justify-content: center;
  height: 100vh;
}
</style>
