<template>
  <div class="baseBeverage" :class="type"></div>
</template>

<script setup lang="ts">
defineProps({
  type: String
});
</script>

<style scoped>
.baseBeverage {
  position: relative;
  width: 100%;
  height: 100%;
  bottom: 0;
  animation: pour-tea 2s;
  z-index: 300;
  border-radius: 0.2em 0.2em 1em 1em; 
}

.baseBeverage.Coffee {
  background-color: #3b2405;
}

.baseBeverage.Green-Tea {
  background-color: #b6cd7d;
}

.baseBeverage.Black-Tea {
  background-color: #a65722;
}

</style>
