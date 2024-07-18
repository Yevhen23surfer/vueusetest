<script setup lang="ts">
// import { useBattery } from '@vueuse/core';
// const battery = useBattery();

// import { useOnline } from '@vueuse/core';
// const online = useOnline();

import { useGeolocation } from '@vueuse/core';
const { coords, locatedAt, error } = useGeolocation();
</script>

<template>
 <!-- {{ battery }} -->
 <!-- Online: {{ online }} -->

    <pre lang="json">{{ 
    JSON.stringify(
        {
            coords: {
                accuracy: coords.accuracy,
                lalitude: coords.lalitude,
                longtitude: coords.longtitude,
                altitude: coords.altitude,
                altitudeAccuracy: coords.altitudeAccuracy,
                heading: coords.heading,
                speed: coords.speed,
            },
            locatedAt: locatedAt,
            error: error ? error.message : error,
        },
        null,
    ) }}</pre>
</template>

<style>
* {
    font-size: 1.5rem;
}
</style>