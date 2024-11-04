<template>
  <div 
  class="baseBeverage" :style="{backgroundColor: props.color}"
  >
  <!-- <div 
  class="baseBeverage" :style="{backgroundColor: bases.find((b)=>b.id==currentBase)?.color ||  "red"}"
  > -->
  </div>
</template>

<script setup lang="ts">
import { computed, defineProps} from 'vue';

//import { bases,currentBase } from "../stores/beverage.ts";

const props = defineProps<{  
    name: string;
    color: string;  
}>();

// const baseColor = computed(() => "red");
</script>

<style scoped>
.baseBeverage {
  position: relative;
  width: 100%;
  height: 100%;
  bottom: 0;
  animation: pour-tea 2s;
  z-index: 300;
  /* // border-radius: 0.05em 0.05em 2.2em 2.2em; */
}
</style>
