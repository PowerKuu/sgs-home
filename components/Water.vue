<script setup lang="ts">
const props = defineProps<{
    light: {
        x: number,
        y: number,
        rotation: number,
    }
}>()
</script>

<template>
    <div class="rays"></div>
    <div class="water"></div>
    <div class="water light-layer"></div>
</template>

<style scoped lang="scss">
.water, .rays {
    pointer-events: none;
}


.water {
    position: absolute;
    
    background: linear-gradient(180deg, rgba(53, 99, 233, 0.98) 1.17%, rgba(25, 53, 136, 0.99) 36.14%, #000D34 96.66%);

    width: 100%;
    height: 100rem;

    margin-top: -2.55rem;

    z-index: 2;
}

.rays {
    position: absolute;
    top: -25rem;
    left: 0;

    background: black;

    width: 100rem;
    height: 100rem;

    background: url(/illustrations/rays.svg) no-repeat;
    background-size: cover;

    z-index: 5;
}

.light-layer {
    z-index: 4;
    background: linear-gradient(180deg, rgba(53, 99, 233, 0.98) 1.17%, rgba(25, 53, 136, 0.99) 36.14%, #000D34 96.66%);
    
    mask-image: 
        url("/icons/logo.svg"), 
        linear-gradient(#fff 0 0);
    mask-repeat: no-repeat;
    mask-position: center;

    mask-composite: exclude;
    
    mask-position: 50% 20%;
}
</style>