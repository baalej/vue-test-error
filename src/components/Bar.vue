<script setup>
import { ref, computed } from 'vue';

const props = defineProps({
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
  return {transform: `rotate(${props.index * (360 / props.total)}deg)`,}
})

const inputValue = ref(props.progress)
</script>

<template>
  <li
  :style="styles"
  >
    <input 
    type="range" 
    min="0"
    :value="props.progress"
    max="100"
    @input="handleInput"
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