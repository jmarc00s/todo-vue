<template>
  <div id="task-input-container">     

      <form class="form-group form-inline"> 
        <input 
            class="form-control"
            placeholder="Inserir tarefa"
            v-model="task" 
            type="text" 
            id="taskDescription">

        <button 
          v-on:click="emitirTarefa()"
          type="button"
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
      if(!this.task) return;
      this.$emit('tarefa-adicionada', this.task);
      this.task = '';
    }
  },
  data() {
    return {
      task: '',
    }
  }  

}
</script>

<style>

</style>