<script setup lang="ts">
import { useLocalStorage, useSessionStorage } from '@vueuse/core';
const name = useLocalStorage('name', 'William');
const favoriteFood = useSessionStorage('favoriteFood', 'pizza');
</script>

<template>
    <input type="text" v-model="name" />
    <input type="text" v-model="favoriteFood" />
</template>
