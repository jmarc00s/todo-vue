<template>
  <div 
        class="tarefa mr-3" 
        @click="toggleConcluirTarefa(tarefa)"
        :class="{'tarefa-concluida': tarefa.concluida}">
    {{tarefa.descricao}}        
  </div>
</template>

<script>
export default {
    props: {
        tarefa: Object
    },
    methods: {
        toggleConcluirTarefa(tarefa){
            tarefa.concluida = !tarefa.concluida;
        }
    },
    data() {
        return {
            
        }
    }
}
</script>

<style>
.tarefa {
    background-color: #d9534f;   
    height: 80px;
    min-width: 100px;
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;
    border-radius: 5px;
    box-shadow: rgba(0, 0, 0, 1);
}
.tarefa-concluida {
    background-color: #5cb85c;
}
</style>