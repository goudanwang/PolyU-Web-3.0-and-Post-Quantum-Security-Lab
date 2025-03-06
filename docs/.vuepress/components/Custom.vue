<template>
  <div class="my-custom-content">
    {{ message }}
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const message = ref('Hello from Custom Component!');
</script>

<style scoped>
.my-custom-content {
  font-size: 20px;
  color: blue;
}
</style>