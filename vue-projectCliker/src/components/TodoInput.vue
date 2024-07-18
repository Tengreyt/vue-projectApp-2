<template>
  <div class="todo-input">
    <input v-model="newTodo" @keyup.enter="submitTodo" placeholder="Добавить новую задачу" />
    <button @click="submitTodo">Добавить</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newTodo: ''
    };
  },
  methods: {
    submitTodo() {
      if (this.newTodo.trim() !== '') {
        this.$emit('add-todo', this.newTodo.trim());
        this.newTodo = '';
      }
    }
  }
};
</script>

<style scoped>
.todo-input input {
  width: calc(100% - 22px);
  padding: 10px;
  margin-bottom: 10px;
}

.todo-input button {
  padding: 10px;
  margin-bottom: 10px;
  cursor: pointer;
}
</style>
