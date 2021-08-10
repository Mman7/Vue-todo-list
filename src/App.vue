<template>
  <TextInput @addTodo="addTodo" />
  <TodoList @deleteData="deleteData" :todoItem="todoItem" />
</template>

<script>
import TextInput from "./components/TextInput.vue";
import TodoList from "./components/TodoList.vue";
export default {
  name: "App",
  components: {
    TextInput,
    TodoList,
  },
  data() {
    return {
      todoItem: [],
    };
  },
  created() {
    this.todoItem = [
      // {
      //   id: 1,
      //   text: "testing my dude",
      // },
      // {
      //   id: 2,
      //   text: "Testing Two My Dude",
      // },
      // {
      //   id: 3,
      //   text: "just a random text",
      // },
    ];
  },
  methods: {
    addTodo(text) {
      this.todoItem = [
        ...this.todoItem,
        {
          id: Math.random() * 10000,
          text: text,
        },
      ];
    },
    deleteData(id) {
      this.todoItem = this.todoItem.filter((object) => object.id !== id);
      console.log(id);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 0;
}
</style>
