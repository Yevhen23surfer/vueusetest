<script setup>
import {ref} from 'vue';
import { onKeyStroke } from '@vueuse/core';

onKeyStroke('ArrowDown', (e) => {
    e.preventDefault();
    position.value.y += 5;
});
onKeyStroke('ArrowUp', (e) => {
    e.preventDefault();
    position.value.y -= 5;
})

const position = ref({ x: 0, y: 0 });
</script>

<template>
    <div class="ball"></div>
</template>

<style>
.ball {
    width: 10px;
    height: 10px;
    border-radius: 50%;
    background-color: red;
    position: absolute;
    top: v-bind(position.y + 'px');
    left: v-bind(position.x + 'px');
}
</style>