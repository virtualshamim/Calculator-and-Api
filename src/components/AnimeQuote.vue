<script setup>
import { ref, onMounted } from 'vue';
const quoteData = ref({});
const fetchQuote = async () => {
  const response = await fetch('https://animechan.xyz/api/random');
  quoteData.value = await response.json();
};

onMounted(fetchQuote);
</script>
<template>
    <div>
      <h2>Anime Quote</h2>
      <p v-if="quoteData.id">ID: {{ quoteData.id }}</p>
      <p v-if="quoteData.quote">Quote: {{ quoteData.quote }}</p>
      <p v-if="quoteData.anime">Anime: {{ quoteData.anime }}</p>
      <p v-if="quoteData.character">Character: {{ quoteData.character }}</p>
      <button @click="fetchQuote">Get New Quote</button>
    </div>
  </template>
  