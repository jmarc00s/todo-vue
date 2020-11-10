<template>
  <div class="lista-tarefas">
      <tarefa v-for="tarefa in tarefas" :key="tarefa" :tarefa="tarefa" />
  </div>
</template>

<script>
import Tarefa from './Tarefa';
export default {
    components: {
        Tarefa
    },
    props: ['tarefas'],

    methods: {

    }, 

    data() {
        return {

        }
    }

}
</script>

<style>

</style>