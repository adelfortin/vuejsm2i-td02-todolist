<template>
  <button @click="emitRemoveTask" class="remove-button">
    🗑️ Supprimer
  </button>
</template>

<script>
export default {
  name: 'TaskRemove',
  methods: {
    // Emit an event to signal task removal
    emitRemoveTask() {
      this.$emit('remove-task');
    }
  }
};
</script>
<style scoped>
.remove-button {
  background-color: #fa8072; /* Rouge Saumon */
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  padding: 5px 10px;
  font-size: 0.8rem;
  line-height: 1;
  display: flex;
  align-items: center;
}

.remove-button:hover {
  background-color: #e9967a; /* Rouge Saumon foncé */
}
</style>
