<script setup>
import { useTitle } from '@vueuse/core';
const title = useTitle();
console.log('page title', title.value);
</script>

<template>
  <input type="text" />
</template>

<style scoped>

</style>
