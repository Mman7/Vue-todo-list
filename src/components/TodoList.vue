<template>
  <div class="todo-list" :key="todo.id in todoItem" v-for="todo in todoItem">
    <TodoItem :todo="todo" @deleteData="deleteData" />
  </div>
</template>

<script>
import TodoItem from "./TodoItem.vue";
export default {
  name: "TodoList",
  components: { TodoItem },
  props: {
    todoItem: Array,
  },
  emits: ["deleteData "],
  methods: {
    deleteData(id) {
      this.$emit("deleteData", id);
    },
  },
};
</script>

<style lang="scss" scoped>
.todo-list {
  padding: 0.5em;
}
</style>
