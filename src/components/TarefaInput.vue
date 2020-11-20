<template>
  <div id="task-input-container">     

      <form @submit.prevent class="tarefa-form form-group form-inline w-100"> 
        <input 
            class="form-control w-75"
            placeholder="Inserir tarefa"
            v-model="tarefa" 
            type="text" 
            id="taskDescription">

        <button 
          v-on:click="emitirTarefa()"
          type="submit"
          class="btn btn-primary">
          +
        </button>
              
      </form>      
  </div>
</template>

<script>
export default {
  methods: {
    emitirTarefa() {
      if(!this.tarefa) return;
      this.$emit('tarefa-adicionada', this.tarefa);
      this.tarefa = '';
    }
  },
  data() {
    return {
      tarefa: '',
    }
  }  

}
</script>

<style scoped>
.tarefa-form {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>