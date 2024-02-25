<script setup>
import { ref } from 'vue';

const operand1 = ref(0);
const operand2 = ref(0);
const operator = ref('+');
const result = ref(null);
const error = ref(null);

function calculate() {
  switch (operator.value) {
    case '+':
      result.value = operand1.value + operand2.value;
      error.value = null;
      break;
    case '-':
      result.value = operand1.value - operand2.value;
      error.value = null;
      break;
    case '*':
      result.value = operand1.value * operand2.value;
      error.value = null;
      break;
    case '/':
      if (operand2.value === 0) {
        error.value = 'Error: Division by zero';
        result.value = null;
      } else {
        result.value = operand1.value / operand2.value;
        error.value = null;
      }
      break;
  }
}
</script>

<template>
    <div class="flex flex-col p-4 border rounded-md">
        <div class="flex flex-row space-x-2">
        <input type="number" v-model="operand1" placeholder="Operand 1" class="p-2 text-black border rounded-md" />
        <select v-model="operator" class="p-2 text-black border rounded-md">
            <option value="+">+</option>
            <option value="-">-</option>
            <option value="*">*</option>
            <option value="/">/</option>
        </select>
        <input type="number" v-model="operand2" placeholder="Operand 2" class="p-2 text-black border rounded-md" />
        </div>
        <button type="button" @click="calculate" class="w-full py-2 mt-2 text-white bg-blue-500 rounded-md">Calculate</button>
        <div v-if="result" class="mt-4 font-bold text-center">{{ result }}</div>
    </div>
</template>

<style scoped>

</style>