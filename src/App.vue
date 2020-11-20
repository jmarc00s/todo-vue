<template>
  <div id="app">
    <h1>Tarefas</h1>

    <progresso class="progresso" :tarefas="tarefas"></progresso>
    <task-input class="tarefa-form" v-on:tarefa-adicionada="adicionarTarefa($event)"/>
    <lista-tarefas class="lista-tarefas" :tarefas="tarefas" />   
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
  width: 100%;
  background: rgb(2,0,36);
  background: linear-gradient(90deg, rgba(2,0,36,1) 0%, rgba(21,57,36,1) 23%, rgba(0,212,255,1) 100%);
  color: white;
}
.progresso {
  width: 60%;  
}
.lista-tarefas {
  width: 60%;
}
.tarefa-form {
  width: 40%;
}
</style>
