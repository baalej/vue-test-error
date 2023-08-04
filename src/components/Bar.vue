<script setup>
import { ref, computed } from 'vue';

const { index, progress, total } = defineProps({
  index: {
    type: Number,
    required: true
  },
  progress: {
    type: Number,
    required: true
  },
  total: {
    type: Number,
    required: true
  }
})

const styles = computed(() => {
  return {transform: `rotate(${index * (360 / total)}deg)`,}
})

const inputValue = ref(progress)
</script>

<template>
  <li
  :style="styles"
  >
    <input 
    type="range" 
    min="0"
    :value="inputValue"
    max="100"
    >  
  </li>
</template>

<style scoped>
li {
  position: absolute;
  top: 0;
  left: 0;
  transform-origin: left;
}

li input {
  width: 128px;
  transform: translateX(50%);
}
</style>