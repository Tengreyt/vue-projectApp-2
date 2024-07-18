<template>
  <li class="todo-item">
    <span :class="{ done: todo.completed }" @click="$emit('toggle')">{{ todo.text }}</span>
    <button @click="$emit('remove')">Удалить</button>
  </li>
</template>

<script>
export default {
  props: {
    todo: {
      type: Object,
      required: true
    }
  }
};
</script>

<style scoped>
.todo-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 5px;
}

.todo-item span {
  flex-grow: 1;
  cursor: pointer;
}

.todo-item .done {
  text-decoration: line-through;
  color: grey;
}

.todo-item button {
  cursor: pointer;
}
</style>
