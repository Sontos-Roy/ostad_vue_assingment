<script setup>
import { ref } from 'vue';

const quote = ref(null);
const error = ref(null);

async function fetchQuote() {
  try {
    const response = await fetch('https://animechan.xyz/api/random');
    if (!response.ok) {
      throw new Error(`Network response was not ok (${response.status})`);
    }
    quote.value = await response.json();
    error.value = null;
  } catch (error) {
    console.error('Error fetching quote:', error);
    error.value = 'Error fetching quote';
  }
}
</script>

<template>
    <div class="flex flex-col p-4 border rounded-md">
        <button type="button" @click="fetchQuote" class="py-2 mb-2 text-white bg-blue-500 rounded-md">Get Random Quote</button>
        <div v-if="quote" class="text-lg">
        <p>"{{ quote.quote }}"</p>
        <span class="font-italic">- {{ quote.character }}, {{ quote.anime }}</span>
        </div>
        <div v-if="error" class="mt-2 text-red-500">{{ error }}</div>
    </div>
</template>

<style scoped>

</style>