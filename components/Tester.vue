<template>
    <div class="water">
        <div class="light-layer"></div>
    </div>
</template>

<style scoped lang="scss">
.water {
    position: absolute;
    width: 100%;
    height: 100rem;
    margin-top: -2.55rem;
    background: linear-gradient(180deg, rgba(53, 99, 233, 0.98) 1.17%, rgba(25, 53, 136, 0.99) 36.14%, #000D34 96.66%);
}

.light-layer {
    position: absolute;

    height: 100vh;
    width: 100vw;

    background: white;
    mask-image: url("https://i.ibb.co/FzmCjLL/Jqtz.png");
    mask-repeat: no-repeat;
    mask-composite: exclude;

    mask-position: 1000px 1px;
}
</style>