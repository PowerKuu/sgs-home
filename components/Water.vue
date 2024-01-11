<script setup lang="ts">
const props = defineProps<{
    light: {
        x: number,
        y: number,
        rotation: number,
    }
}>()

const waterLayer = ref<HTMLElement>()

const svgWidth = ref(199)


const imgBase64 = computed(() => {
    return btoa(`<svg width="${svgWidth.value}" height="544" viewBox="0 0 629 544" fill="none" xmlns="http://www.w3.org/2000/svg">
    <path d="M314.5 0L628.434 543.75H0.565796L314.5 0Z" fill="white"/>
    </svg>`)
})

const done = computed(() => {
    console.log("rendering")
    return `data:image/svg+xml;base64,${imgBase64.value}`
})

onMounted(() => {
    watchEffect(() => {
        waterLayer.value?.style.setProperty("mask-image", `url("${done.value}"), linear-gradient(#fff 0 0`)
    })
    setInterval(() => {
    }, 1000)
})
</script>

<template>
    <div class="rays"></div>
    <div class="water"></div>



    <div ref="waterLayer" class="water-layer"></div>
</template>

<style scoped lang="scss">
.water, .rays {
    pointer-events: none;
}


.rays {
    position: absolute;
    z-index: 5;

    top: -25rem;
    left: 0;

    background: black;

    width: 100rem;
    height: 100rem;

    background: url(/illustrations/rays.svg) no-repeat;

    background-size: cover;
}

.water-layer {
    position: absolute;
    z-index: 4;

    top: -2.5rem;


    width: 100%;
    height: 100rem;

    background: linear-gradient(180deg, rgba(53, 99, 233, 0.98) 1.17%, rgba(25, 53, 136, 0.99) 36.14%, #000D34 96.66%);

    mask-composite: exclude;
    mask-repeat: no-repeat;

    mask-position: 50% 20%;
}
</style>