<template>
  <ul class="task-list">
    <li v-for="(task, index) in tasks" :key="index" class="task-item">
      {{ task }}
      <!-- Poue supprimer une tâche  -->
      <TaskRemove @remove-task="() => removeTask(index)" />
    </li>
  </ul>
</template>

<script>
import TaskRemove from './TaskRemove.vue';

export default {
  name: 'TaskList',
  components: {
    TaskRemove
  },
  props: {
    tasks: Array
  },
  methods: {
    removeTask(index) {
      this.$emit('remove-task', index);
    }
  }
};
</script>

<style scoped>
.task-list {
  list-style-type: none;
  padding-left: 0;
  margin-left: 0;
  text-align: left;
}

.task-item {
  background: #fff;
  margin-bottom: 10px;
  padding: 10px 20px;
  border-radius: 4px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
  display: flex; 
  justify-content: space-between; 
  align-items: center; 
}

.task-item > :first-child {
  margin-right: 10px;
}
</style>

