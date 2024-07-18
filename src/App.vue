<script setup lang="ts">
// import { usePageLeave, whenever } from '@vueuse/core';
// const isLeft = usePageLeave();
// const unwatch = whenever(isLeft, () => {
//     alert('Are you sure you want to go?');
//     unwatch();
// });

import { usePointer } from '@vueuse/core';
import { onMounted, reactive, ref, watch } from 'vue';
const pointer = reactive(usePointer());
const canvas = ref  (null);
watch(pointer, () => {
    if(pointer.pressure === 0) return
    const ctx = canvas.value.getContext('2d');
    ctx.fillStyle = 'red';
    ctx.fillRect(pointer.x - 20, pointer.y -20, 10, 10);
});
onMounted(()=> {
    canvas.value.height = document.body.clientHeight;
    canvas.value.width = document.body.clientWidth;
})

</script>

<template>
<!-- {{ isLeft }} -->
<canvas ref="canvas"></canvas>
</template>

<style>

</style>