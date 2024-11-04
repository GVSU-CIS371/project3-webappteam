<template>
  <div class="syrup" :style="{ backgroundColor: props.color}"></div>
</template>

<script setup lang="ts">
import { defineProps, computed } from 'vue';

const props = defineProps<{
  name: string;
  color: string;
}>();

//const syrupColor = computed(() => props.syrup?.color);
</script>
<style lang="scss" scoped>
.syrup {
  transform: translateY(400%);
  background-color: #c6c6c6;
  position: relative;
  width: 100%;
  height: 20%;
  animation: pour-tea 2s 1s forwards;
  z-index: 2;
}
</style>
