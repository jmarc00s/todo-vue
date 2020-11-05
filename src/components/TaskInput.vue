<template>
  <div id="task-input-container">
      <form class="form-group form-inline">  

        <input 
            class="form-control"
            placeholder="Tarefa"
            v-model="task" 
            type="text" 
            id="taskDescription">

        <button 
          :click="emitirTarefa()"
          type="submit"
          class="btn btn-primary">
          Adicionar tarefa
        </button>

      </form>      
  </div>
</template>

<script>
export default {
  methods: {
    emitirTarefa: () => {
      this.$emit('tarefa-adicionada', this.task);
    }
  },
  data: () => {
    return {
      task: undefined,
    }
  }  

}
</script>

<style>

</style>