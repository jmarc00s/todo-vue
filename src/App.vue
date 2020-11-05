<template>
  <div id="app">
   <task-input v-on:tarefa-adicionada="adicionarTarefa($event)"/>
  </div>
</template>

<script>

import TaskInput from './components/TaskInput';

export default {
  components: {
    TaskInput
  },
  methods: {
    adicionarTarefa(tarefa){
      console.log(tarefa);
    }
  },
  data: () => {
    return {
      tarefas: []
    }
  }
}
 
</script>

<style>
#app {
  display: flex;
  align-items: center;
  align-content: center;  
  flex: 1 0 auto;
  justify-content: center;
  height: 100vh;
}
</style>
