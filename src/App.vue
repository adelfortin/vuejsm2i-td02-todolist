<template>
  <div id="app">
    <TaskAdd @add-task="addTask" />
    <TaskList :tasks="taskList" @remove-task="removeTask" />
  </div>
</template>

<script>
import TaskAdd from './components/TaskAdd.vue';
import TaskList from './components/TaskList.vue';

export default {
  name: 'App',
  components: {
    TaskAdd,
    TaskList
  },
  data() {
    return {
      taskList: []
    };
  },
  methods: {
    addTask(newTask) {
      this.taskList.push(newTask);
    },
    removeTask(index) {
      this.taskList.splice(index, 1);
    }
  }
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

body {
  background-color: #ecf0f1;
  margin: 0;
  font-family: 'Source Sans Pro', sans-serif;
}

h1 {
  font-weight: 300;
  color: #2c3e50;
}
</style>
