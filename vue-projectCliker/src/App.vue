<template>
  <div class="app">
    <h1>Список дел</h1>
    <TodoInput @add-todo="addTodo" />
    <TodoList :todos="todos" @remove-todo="removeTodo" @toggle-complete="toggleComplete" />
  </div>
</template>

<script>
import TodoInput from './components/TodoInput.vue';
import TodoList from './components/TodoList.vue';

export default {
  components: {
    TodoInput,
    TodoList
  },
  data() {
    return {
      todos: []
    };
  },
  methods: {
    addTodo(todoText) {
      this.todos.push({ text: todoText, completed: false });
    },
    removeTodo(index) {
      this.todos.splice(index, 1);
    },
    toggleComplete(index) {
      this.todos[index].completed = !this.todos[index].completed;
    }
  }
};
</script>

<style scoped>
.app {
  max-width: 400px;
  margin: 0 auto;
  text-align: center;
}
</style>
