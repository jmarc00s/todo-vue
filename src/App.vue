<template>
  <div id="app">
    <progresso style="width: 250px" :tarefas="tarefas"></progresso>

    <h1>Tarefas</h1>

    <task-input v-on:tarefa-adicionada="adicionarTarefa($event)"/>

    <lista-tarefas :tarefas="tarefas" />   
  </div>
</template>

<script>

import TaskInput from './components/TarefaInput';
import ListaTarefas from './components/ListaTarefas';
import Progresso from './components/Progresso';

export default {
  components: {
    TaskInput,
    ListaTarefas,
    Progresso
  },
  methods: {
    adicionarTarefa(descricaoTarefa){

      if(this.tarefas.some((tarefa) => tarefa.descricao === descricaoTarefa)){
        return;
      }

      this.tarefas.push({
        descricao: descricaoTarefa,
        concluida: false
      });

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
  background: rgb(2,0,36);
  background: linear-gradient(90deg, rgba(2,0,36,1) 0%, rgba(21,57,36,1) 23%, rgba(0,212,255,1) 100%);
  color: white;
}
</style>
