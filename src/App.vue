<template>
  <div id="app">
    <input
      type="text"
      placeholder="Type something..."
      v-model="inputValue"
      @keyup="inputContainsNumbers"
    />
    <p>
      Contains number:
      <span v-if="inputContainsNumber">✅ True</span>
      <span v-else>❌ False</span>
    </p>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      inputValue: null,
      inputContainsNumber: false,
    };
  },
  methods: {
    inputContainsNumbers() {
      const numbers = /\d/;
      this.inputContainsNumber = numbers.test(this.inputValue);
    },
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000000;
  margin-top: 60px;
}
input {
  font-size: 16px;
  padding: 4px;
  border: 1px solid rgb(34, 34, 34);
  outline: none;
}
</style>
