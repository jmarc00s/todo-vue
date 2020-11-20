<template>    
  <div>
      <div 
            class="tarefa" 
            @click="toggleConcluirTarefa(tarefa)"
            :class="{'tarefa-concluida': tarefa.concluida}">
        {{tarefa.descricao}}        
    </div>
    <div @click="emitRemover(tarefa)" class="botao-remover">
    </div>
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
        },
        emitRemover(tarefa) {
            const resposta = confirm('Deseja remover esta tarefa? ');
            if(resposta){
                this.$emit('remover-tarefa', tarefa);
            }
        }
    },
    data() {
        return {
            
        }
    }
}
</script>

<style>
.botao-remover:after{    
  display: inline-block;
  content: "\00d7"; /* This will render the 'X' */
  position: absolute;
  top: 0 ;
  right: 35px;
  font-size: 24px;
  cursor: pointer;  
}
.tarefa {
    margin: 0 10px 10px 0;
    background-color: #d9534f;   
    height: 150px;
    min-width: 200px;    
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;
    border-radius: 5px;
    box-shadow: rgba(0, 0, 0, 1);
    padding: 8px;
    border-left: solid 15px rgba(0, 0, 0, 0.2);
    font-size: 25px;
}
.tarefa-concluida {
    background-color: #5cb85c;
    text-decoration-line: line-through;
}
</style>