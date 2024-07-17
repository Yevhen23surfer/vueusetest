<script setup>
import { useDark, useToggle, useColorMode } from '@vueuse/core'
const isDark = useDark(); // true or false
const colorMode = useColorMode({
    modes: {
        dim: 'dim',
        cafe: 'cafe',
    },
    attribute: 'theme',
}); // light or dark
const toggleDark = useToggle(isDark);
</script>

<template>
    {{ colorMode }}
    <button @click="colorMode = 'dark'">Dark Mode</button>
    <button @click="colorMode = 'light'">Light Mode</button>
    <button @click="colorMode = 'cafe'">Cafe Mode</button>
    <button @click="colorMode = 'dim'" >Dim Mode</button>
</template>

<style>
[theme="dark"]{
    background: black;
    color: white;
}
[theme="light"].dark{
    background: black;
    color: white;
}
[theme='dim']{
    background: rgb(0, 212, 71);
    color: rgb(0, 0, 0);
}
[theme='cafe']{
    background: burlywood;
    color: rgb(65, 26, 26);
}
</style>