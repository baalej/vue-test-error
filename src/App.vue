<script setup>
import { ref } from 'vue';
import Star from './components/Star.vue'
import Bar from './components/Bar.vue';

const count = ref(20)
const progress = 50
</script>
  
<template>
  <input type="number" v-model="count">
  <main>
    <Star
    :total="count"
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
}
</style>
