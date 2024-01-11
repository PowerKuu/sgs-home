<script setup lang="ts">

</script>

<template>
    <SystemTopnav>
        <template #left>
            <SystemLogo></SystemLogo>
        </template>

        <template #right>
            <SystemP>Button</SystemP>
            <SystemButton>Primary button</SystemButton>
        </template>
    </SystemTopnav>

    <SystemFlex class="design" gap="1rem" direction="column">
        <SystemH1>Heading 1 text</SystemH1>
        <SystemH2>Heading 2 text</SystemH2>
        <SystemH3>Heading 3 text</SystemH3>

        <SystemP>Paragraph text</SystemP>
        <SystemPBold>Bold paragraph text</SystemPBold>
        <SystemPUnderline>Underline paragraph text</SystemPUnderline>

        <SystemFlex gap="1rem" direction="row">
            <SystemButton>Button</SystemButton>
            <SystemButton border="var(--secondary)" color="var(--secondary)" background="var(--background)">Primary button</SystemButton>
            <SystemButton disabled>Disabled button</SystemButton>
        </SystemFlex>

        <SystemLogo></SystemLogo>
    </SystemFlex>
    <Wave></Wave>
</template>

<style scoped lang="scss">
.design {
    padding: 5rem;
}
</style>