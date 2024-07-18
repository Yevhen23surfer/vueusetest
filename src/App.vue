// VueUse Utilities: computedAsync and logic utils
<script setup lang="ts">
import { ref, computed } from 'vue';
import { computedAsync } from '@vueuse/core';
const id = ref(1);
const url = computed(
  () => `https://jsonplaceholder.typicode.com/posts/${id.value}`
);
const post = computedAsync(
  () => fetch(url.value).then((res) => res.json())
);
</script>

<template>
  <input type="number" v-model="id">
{{ post }}
</template>
