<template>
  <div v-if="existeTarefaConcluida()" class="mb-3">
     <div class="progress w-100" style="height: 30px">
         <div class="progress-bar bg-success progress-bar-stripped" :style="{width: porcentagemConcluida() + '%'}">
             <span class="descricao-porcentagem">{{porcentagemConcluida() + '%'}}</span>
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

<style scoped>

.descricao-porcentagem {
    font-size: 18px;
}
</style>