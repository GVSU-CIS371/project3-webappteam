<template>
  <div>
    <!-- <Beverage :isIced="currentTemp === 'Cold'" /> -->
    <ul>
      <li>
        <template v-for="temp in temps" :key="temp">
          <input
            type="radio"
            name="temperature"
            :id="`r${temp}`"
            :value="temp"
            v-model="currentTemp"
          />
          <label :for="`temp-${temp}`">{{ temp }}</label>
        </template>
      </li>
      <li>
        <template v-for="base in bases" :key="base.id">          
          <input
            type="radio"
            name="base"
            :id="`r${base.id}`"
            :value="base.id"
            v-model="currentBase"
          />
          <label :for="`base-${base.id}`">{{  base.name }}</label>
        </template>
      </li>
      <li>
        <template v-for="creamer in creamers" :key="creamer.id">
          <input
            type="radio"
            name="creamer"
            :id="`r${creamer.id}`"
            :value="creamer.id"
            v-model="currentCreamer"
          />
          <label :for="`creamer-${creamer.id}`">{{ creamer.name }}</label>
        </template>
      </li>
      <li>
        <template v-for="syrup in syrups" :key="syrup.id">
          <input
            type="radio"
            name="syrup"
            :id="`r${syrup.id}`"
            :value="syrup.id"
            v-model="currentSyrup"
          />
          <label :for="`syrup-${syrup.id}`">{{ syrup.name }}</label>
        </template>
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import { computed } from "vue";
import Beverage from "./components/Beverage.vue";
//updated the import statement to include all aspects of the drink
import { temps, bases, creamers, syrups, currentTemp, currentBase, currentCreamer, currentSyrup } from "./stores/beverage";

//compute the properties and act according to the binded properties
const selectedBaseColor = computed(() => {
  const base = bases.value.find(b => b.id === currentBase.value);
  return base ? base.color : "#ffffff";//set default to hex #ffffff if not found
});

const selectedCreamerColor = computed(() => {
  const creamer = creamers.value.find(c => c.id === currentCreamer.value);
  return creamer ? creamer.color : "transparent";//set default to transparent if not found
});

const selectedSyrupColor = computed(() => {
  const syrup = syrups.value.find(s => s.id === currentSyrup.value);
  return syrup ? syrup.color : "#ffffff";//set default to hex #ffffff if not found
});

</script>


<style lang="scss">
body,
html {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  background-color: #6e4228;
  background: linear-gradient(to bottom, #6e4228 0%, #956f5a 100%);
}
ul {
  list-style: none;
}
</style>
