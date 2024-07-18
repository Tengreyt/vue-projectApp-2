<template>
  <ul class="todo-list">
    <TodoItem
      v-for="(todo, index) in todos"
      :key="index"
      :todo="todo"
      @remove="removeTodo(index)"
      @toggle="toggleComplete(index)"
    />
  </ul>
</template>

<script>
import TodoItem from './TodoItem.vue';

export default {
  components: {
    TodoItem
  },
  props: {
    todos: {
      type: Array,
      required: true
    }
  },
  methods: {
    removeTodo(index) {
      this.$emit('remove-todo', index);
    },
    toggleComplete(index) {
      this.$emit('toggle-complete', index);
    }
  }
};
</script>

<style scoped>
.todo-list {
  list-style-type: none;
  padding: 0;
}
</style>
