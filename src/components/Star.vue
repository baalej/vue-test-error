<script setup>
import Bar from './Bar.vue'

const props = defineProps({
  total: {
    type: Number,
    required: true
  },
  progress: {
    type: Number,
    required: true
  }
})
</script>

<template>
  <ul class="star">
    <Bar 
    v-for="(item, index) in props.total"
    :key="index"
    :index="index"
    :progress="props.progress"
    :total="props.total"
    ></Bar>
  </ul>
</template>

<style scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
  position: relative;
}
</style>