<script setup>
import { ref, watch } from 'vue';
import { useMagicKeys, whenever } from '@vueuse/core';

const { ctrl_c } = useMagicKeys();
whenever(ctrl_c, (pressed) => console.log(pressed));

</script>

<template>

</template>

<style>

</style>