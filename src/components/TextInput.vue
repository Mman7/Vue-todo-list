<template>
  <div>
    <input
      type="text"
      :value="this.inputText"
      @input="inputHandle($event.target.value)"
    />
    <button @click="addTodo(text)">
      <i class="far fa-plus-square"></i>
    </button>
  </div>
</template>

<script>
export default {
  name: "TextInput",
  data() {
    return {
      inputText: "",
    };
  },
  emits: ["addTodo"],
  methods: {
    inputHandle(value) {
      this.inputText = value;
    },
    addTodo() {
      if (this.inputText === "") return;
      this.$emit("addTodo", this.inputText);
      this.inputText = "";
    },
  },
};
</script>

<style lang="scss" scoped>
div {
  padding: 1em;
  display: flex;
  justify-content: center;
  align-content: center;
  input {
    padding: 0.5em;
    font-size: 1rem;
    outline: none;
    border: none;
    border-radius: 10px;
    border: none;
  }
  button {
    cursor: pointer;
    background: none;
    border: none;
    color: white;
    font-size: 2rem;
  }
}
</style>
