<script setup>
import { ref } from 'vue';
import Star from './components/Star.vue'

const total = ref(20)
const progress = ref(50)
</script>
  
<template>
  <input 
  type="number" 
  v-model="total"
  min="0"
  >
  <input 
  type="number" 
  v-model="progress"
  min="0"
  max="100"
  >
  <main>
    <Star
    :total="total"
    :progress="progress"
    />
  </main>
</template>

<style scoped>
main {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 100%;
  display: flex;
  justify-content: center;
}
</style>
