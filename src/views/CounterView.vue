<script setup lang="ts">
import { useCounterStore } from '@/stores/counter'
import { storeToRefs } from 'pinia'
const counterStore = useCounterStore()
const { count } = storeToRefs(counterStore)
const { increment, resetCounter } = counterStore
</script>

<template>
  <div class="flex flex-col items-center pt-24">
    <div class="counter">
      <h1>This is the counter page</h1>
      <h2>Current count is {{ count }}</h2>
      <button @click="increment">+1</button>
      <button @click="resetCounter">Reset</button>
    </div>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .counter {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
}
button {
  background-color: lightgreen;
  color: #353535;
  padding: 0.5ch 1ch;
  margin-bottom: 0.5ch;
}
</style>
