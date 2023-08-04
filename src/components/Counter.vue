<script setup>
import { computed, ref } from 'vue';

const count = ref(0)

function handleClick(operation) {
  if (operation === 'increase') {
    count.value = count.value < 10 ? count.value+1 : count.value
  } else {
    count.value = count.value > -10 ? count.value-1 : count.value
  }
}

const classObject = computed(() => ({
  positive: count.value > 0,
  neutral: count.value === 0,
  negative: count.value < 0
}))

const fontSize = computed(() => {
  if (count.value < 0) {
    return count.value * -1
  } else {
    return count.value
  }
})
</script>

<template>
  <p :style="{transform: `scale(${fontSize})`}" :class="classObject">Counter: {{ count }}</p>
  <div class="controls">
    <button @click="handleClick('increase')">more</button>
    <button @click="handleClick('decrease')">less</button>
  </div>
</template>

<style scoped>
.positive {
  color: green;
}

.neutral {
  color: blue;
}

.negative {
  color: red;
}

.controls {
  display: flex;
  gap: 0.5rem;
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translateX(-50%);
}

p {
  text-align: center;
  transition: transform 0.5s;
}
</style>