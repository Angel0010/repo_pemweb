<template>
  <div id="app">
    <input type="text" v-model="expression" />
    <div class="button-container">
      <button v-for="button in buttons" @click="appendToExpression(button)">
        {{ button }}
      </button>
    </div>
    <button @click="calculate">=</button>
    <div id="result">{{ result }}</div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const expression = ref("");
const result = ref("");
const buttons = [
  "1",
  "2",
  "3",
  "+",
  "4",
  "5",
  "6",
  "-",
  "7",
  "8",
  "9",
  "*",
  "0",
  ".",
  "/",
];

const appendToExpression = (value) => {
  expression.value += value;
};

const calculate = () => {
  try {
    result.value = eval(expression.value);
  } catch (error) {
    result.value = "Error";
  }
};
</script>

<style scoped>
/* Styling for your component */
</style>
