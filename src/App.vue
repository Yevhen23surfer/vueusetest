<script setup lang="ts">
import { ref } from 'vue';
import { useTimeoutFn } from '@vueuse/core';
const showAlert = ref(true);
const { start, stop, isPending } = useTimeoutFn(()=>{
  showAlert.value = false;
}, 3000)
</script>

<template>
<transition appear>
<div v-if="showAlert" class="alert" @mouseenter="stop" @mouseout="start">
    Your post has been saved
    <button @click="stop">x</button>
</div>
</transition>

</template>

<style>
.v-enter-active,
.v-leave-active {
  transition: all 0.2s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}
</style>
