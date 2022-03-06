<script setup lang="ts">
import { ref } from 'vue';
import SizeSelector from './components/SizeSelector.vue';

const selectedSize = ref<string>('none')

</script>

<template>
  <h1>Selected Size: {{ selectedSize }}</h1>
  <size-selector :selected-size="selectedSize" @on-size-change="selectedSize = $event" />
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

button {
  width: 75px;
  padding: 5px;
  border: none;
  border-radius: 5px;
  margin-right: 5px;
  cursor: pointer;
}

.active {
  background-color: #000;
  color: #fff;
  transform: all .3s ease-out;
}
</style>
