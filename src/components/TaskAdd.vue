<template>
  <div class="task-add-container">
    <input
      type="text"
      v-model="newTaskName"
      @keyup.enter="emitAddTask"
      placeholder="Ajouter une nouvelle tâche"
      class="task-input"
    />
    <button @click="emitAddTask" class="add-button">Ajouter</button>
  </div>
</template>

<script>
export default {
  name: 'TaskAdd',
  data() {
    return {
      newTaskName: '',
    };
  },
  methods: {
    emitAddTask() {
      if (this.newTaskName.trim() !== '') {
        this.$emit('add-task', this.newTaskName);
        this.newTaskName = '';
      }
    },
  },
};
</script>

<style scoped>
.task-add-container {
  text-align: center;
  margin-bottom: 20px;
}

.task-input {
  padding: 10px;
  margin-right: 10px;
  border: 1px solid #ddd;
  border-radius: 4px;
  width: 70%;
}

.add-button {
  padding: 10px 20px;
  background-color: #5cb85c;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.add-button:hover {
  background-color: #4cae4c;
}
</style>

