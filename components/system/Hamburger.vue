<script setup lang="ts">
const showMenu = ref(false)
</script>

<template>
    <Icon @click="showMenu = !showMenu" name="solar:hamburger-menu-linear" class="hamburger"></Icon>

    <SystemOverlay @click="showMenu = false" v-if="showMenu"></SystemOverlay>

    <SystemFlex v-if="showMenu" class="hamburger-menu" gap="1rem" direction="column">
        <slot></slot>
    </SystemFlex>
</template>

<style scoped lang="scss">
.hamburger {
    width: 2rem;
    height: 2rem;
    cursor: pointer;
}

.hamburger-menu {
    position: fixed;
    top: 0;
    left: 0;
    width: max(40vw, 10rem);
    height: 100%;

    padding: 5rem var(--page-padding);

    background: var(--background);
    backdrop-filter: blur(5px);
}
</style>