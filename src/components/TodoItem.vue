<template>
  <div class="todo-item">
    <h1>{{ todo.text }}</h1>
    <button @click="deleteData(todo.id)">
      <i class="fas fa-trash"></i>
    </button>
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
  border: 3px solid white;
  border-radius: 25px;
  color: white;
}
.todo-item {
  display: flex;
  justify-content: space-between;
  h1 {
    font-size: 1rem;
    word-wrap: break-word;
    overflow: hidden;
  }
  button {
    cursor: pointer;
    background: none;
    outline: none;
    font-size: 1.5rem;
    border: none;
    color: white;
  }
}
</style>
