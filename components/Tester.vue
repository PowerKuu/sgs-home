<template>
    <div class="water light-layer"></div>
</template>

<style scoped lang="scss">
.light-layer {
    position: absolute;

    z-index: 4;
    width: 100%;
    height: 100rem;

    margin-top: -2.55rem;

    background: linear-gradient(180deg, rgba(53, 99, 233, 0.98) 1.17%, rgba(25, 53, 136, 0.99) 36.14%, #000D34 96.66%);
    
    mask-image: 
        url("https://i.ibb.co/FzmCjLL/Jqtz.png"), 
        linear-gradient(#fff 0 0);
    mask-repeat: no-repeat;
    mask-position: center;

    mask-composite: exclude;
    
    mask-position: 50% 20%;
}
</style>