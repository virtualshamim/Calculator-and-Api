<script setup>
import { ref } from 'vue';

const num1 = ref(null);
const num2 = ref(null);
const operator = ref('+');
const result = ref(null);

const calculate = () => {
  switch (operator.value) {
    case '+':
      result.value = parseFloat(num1.value) + parseFloat(num2.value);
      break;
    case '-':
      result.value = parseFloat(num1.value) - parseFloat(num2.value);
      break;
    case '*':
      result.value = parseFloat(num1.value) * parseFloat(num2.value);
      break;
    case '/':
      result.value = parseFloat(num1.value) / parseFloat(num2.value);
      break;
  }
};
</script>
<template>
    <div>
      <h2>Calculator</h2>
      <input type="number" v-model="num1">
      <select v-model="operator">
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="*">*</option>
        <option value="/">/</option>
      </select>
      <input type="number" v-model="num2">
      <button @click="calculate">Calculate</button>
      <p v-if="result !== null">Result: {{ result }}</p>
    </div>
  </template>
  