<template>
  <div>
    <Beverage 
      :isIced="currentTemp === 'Cold'" 
      :base="selectedBase" 
      :creamer="selectedCreamer" 
      :syrup="selectedSyrup"
    />

    <ul>
      <li>
        <label>Temperature</label>
        <template v-for="temp in temps" :key="temp">
          <label>
            <input
              type="radio"
              name="temperature"
              :id="`r${temp}`"
              :value="temp"
              v-model="currentTemp"
            />
            {{ temp }}
          </label>
        </template>
      </li>

      <li>
        <label for="baseSelect">Base Beverage:</label>
        <select id="baseSelect" v-model="selectedBase">
          <option value="Coffee"> Coffee </option>
          <option value="Green-Tea"> Green Tea </option>
          <option value="Black-Tea"> Black Tea </option>
        </select>
      </li>

      <li>
        <label for="creamerSelect">Creamer:</label>
        <select id="creamerSelect" v-model="selectedCreamer">
          <option value="No-Creamer"> No Creamer </option>
          <option value="No-Milk"> Milk </option>
          <option value="Cream"> Cream </option>
          <option value="Half-And-Half"> Half & Half </option>
        </select>
      </li>

      <li>
        <label for="syrupSelect">Syrup:</label>
        <select id="syrupSelect" v-model="selectedSyrup">
          <option value="No-Syrup"> No Syrup </option>
          <option value="Vanilla"> Vanilla </option>
          <option value="Caramel"> Caramel </option>
          <option Value="Hazelnut"> Hazelnut </option>
        </select>
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import Beverage from "./components/Beverage.vue";
import { temps, currentTemp } from "./stores/beverage";
import { ref } from "vue";

const selectedBase = ref("Coffee");
const selectedCreamer = ref("No-Creamer");
const selectedSyrup = ref("No-Syrup");
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
  background: linear-gradient(to bottom, #55311c 0%, #9a725d 100%);
}
ul {
  list-style: none;
}
</style>
