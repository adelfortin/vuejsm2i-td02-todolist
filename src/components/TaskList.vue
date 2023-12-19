<template>
  <div>
    <!-- Champ de saisie pour une nouvelle tâche -->
    <input type="text" v-model="newTaskName" placeholder="Ajouter une nouvelle tâche" />

    <!-- Bouton pour ajouter la tâche à la liste -->
    <button @click="addTask">Ajouter</button>

    <!-- Affichage de la liste des tâches -->
    <ul>
      <li v-for="(task, index) in taskList" :key="index">{{ task }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'TaskList',
  data() {
    return {
      // Nouveau nom de tâche lié au champ de texte
      newTaskName: '',
      // Liste des tâches
      taskList: []
    };
  },
  methods: {
    // Méthode pour ajouter une tâche à la liste
    addTask() {
      if (this.newTaskName.trim() !== '') {
        this.taskList.push(this.newTaskName);
        this.newTaskName = ''; // Réinitialiser le champ de texte
      }
    }
  }
};
</script>

<style scoped>
.task-list-container {
  max-width: 400px;
  margin: 40px auto;
  padding: 20px;
  background: #f9f9f9;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  border-radius: 8px;
}

.task-list-container input[type="text"] {
  width: 70%;
  padding: 10px;
  margin-right: 10px;
  border: 1px solid #ddd;
  border-radius: 4px;
  box-sizing: border-box;
}

.task-list-container button {
  padding: 10px 20px;
  background-color: #5cb85c;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.task-list-container button:hover {
  background-color: #4cae4c;
}

.task-list-container ul {
  list-style: none;
  padding: 0;
  margin-top: 20px;
}

.task-list-container li {
  background: #fff;
  margin-bottom: 10px;
  padding: 10px;
  border-radius: 4px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
}
</style>

