<template>
  <div class="todo-item">
    <h1>{{ todo.text }}</h1>
    <button @click="deleteData(todo.id)">Delete</button>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: {
    todo: Object,
  },
  methods: {
    deleteData(id) {
      this.$emit("deleteData", id);
    },
  },
};
</script>

<style lang="scss" scoped>
div {
  padding: 1em;
  border: 3px solid black;
}
.todo-item {
  display: flex;
  justify-content: space-between;

  button {
    background: none;
    border-radius: 10px;
    outline: none;
    padding: 1em;
  }
}
</style>
