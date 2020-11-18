<template>
  <div v-if="existeTarefaConcluida()">
     <div class="progress w-100">
         <div class="progress-bar progress-bar-stripped" :style="{width: porcentagemConcluida() + '%'}">
             {{porcentagemConcluida() + '%'}}
        </div>         
     </div> 
  </div>
</template>

<script>
export default {
    props: {
        tarefas: Array
    },    
    methods: {
        porcentagemConcluida() {            
            const quantidadeTarefas = this.tarefas.length;
            const quantidadeTarefasConcluidas = this.tarefas.filter((tarefa) => tarefa.concluida).length;
            this.porcentagemTarefasConcluidas =  Math.round((quantidadeTarefasConcluidas/quantidadeTarefas) * 100);
            return this.porcentagemTarefasConcluidas;
        },
        existeTarefaConcluida() {
            return this.tarefas.some((tarefa) => tarefa.concluida);
        }
    },
    data() {
        return {
            porcentagemTarefasConcluidas: undefined
        }
    }
}
</script>

<style>

</style>