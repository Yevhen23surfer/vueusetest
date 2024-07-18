<script setup lang="ts">
import { ref } from 'vue';
import { useBase64 } from '@vueuse/core';
const image = ref('');
const { base64 } = useBase64(image);
</script>

<template>
  <input
    type="file"
    accept="image/png, image/jpeg"
    @change="image = $event.target.files[0]"
  />
  <br />
  <br />
  <img v-if="image" :src="base64" width="300" />
</template>
