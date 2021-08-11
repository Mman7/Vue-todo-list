<template clas>
  <div class="App">
    <TextInput @addTodo="addTodo" />
    <TodoList @deleteData="deleteData" :todoItem="todoItem" />
  </div>
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
    this.todoItem = [];
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
  width: clamp(20rem, 50%, 30rem);
}
body {
  padding: 1em;
  margin: 0;
  background: rgb(0, 219, 255);
  background: linear-gradient(
    120deg,
    rgba(0, 219, 255, 1) 0%,
    rgba(179, 0, 255, 1) 100%
  );
  height: 100vh;
  width: 100vw;
  overflow: hidden;
  display: flex;
  justify-content: center;
}
.App {
  border: 3px solid white;
  border-radius: 25px;
}
</style>
