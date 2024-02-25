<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import RandomQuote from './components/Calculator/RandomQuote.vue'
import Calculator from './components/Calculator/Calculator.vue'
</script>

<template>
  <div class="container p-4 mx-auto">
    <h1 class="mb-4 text-3xl font-bold">Calculator</h1>
    <Calculator />
    <h2 class="mt-8 mb-4 text-2xl font-bold">Random Quote</h2>
    <RandomQuote />
  </div>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
