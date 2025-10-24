<template>
  <div class="syrup" :class="type"></div>
</template>

<script setup lang="ts">
defineProps({
  type: String
});
</script>

<script setup lang="ts"></script>
<style lang="scss" scoped>
.syrup {
  transform: translateY(400%);
  background-color: #c6c6c6;
  position: relative;
  width: 100%;
  height: 20%;
  animation: pour-tea 2s 1s forwards;
  z-index: 2;
  border-radius: 0; 
}

.syrup.Vanilla {
  background-color: #edd9b5;
}
.syrup.Caramel {
  background-color: #c98948;
}
.syrup.Hazelnut {
  background-color: #694c30;
}

</style>
