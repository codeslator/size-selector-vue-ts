<script setup lang="ts">
import { toRefs } from 'vue';

const sizes: string[] = [
  'XS',
  'S',
  'M',
  'L',
  'XL',
  'XXL',
];

interface Props {
  selectedSize: string;
};

interface Emits {
  (event: 'onSizeChange', value: string): void,
}

const props = defineProps<Props>();
const emits = defineEmits<Emits>()

toRefs(props);
</script>

<template>
  <div>
    <button
      type="button"
      v-for="(size, index) in sizes"
      :key="index"
      :class="{ 'active': selectedSize === size }"
      @click="emits('onSizeChange', size)"
    >
      {{ size }}
    </button>
  </div>
</template>

<style>
</style>