<template>
  <div>
    <input
      type="text"
      :value="this.inputText"
      @input="inputHandle($event.target.value)"
    />
    <button @click="addTodo(text)">Add Todo</button>
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
  border: 3px solid black;
}
</style>
