<script setup lang="ts">

</script>

<template>
    <SystemFlex direction="column">
        <SystemFlex class="top-content" justify="space-between" grow="1">
            <SystemFlex class="left" gap="1.5rem" direction="column">
                <SystemH1>Storhet Gjennom Samarbeid</SystemH1>

                <SystemP>SGS Marketing er en totalleverandør innen markedsføringstjenester i Bergen. Vi jobber med alt innenfor nettsider, media, og tilbyr tilpassede tjenester etter dine behov. Ring oss eller send en melding, vi svarer så raskt vi kan.</SystemP>
                
                <SystemFlex>
                    <SystemButton>Kom i gang</SystemButton>
                    <SystemButton border="#00000000" color="var(--primary)" background="#00000000">Kotakt oss</SystemButton>
                </SystemFlex>
            </SystemFlex>

            <SystemFlex class="bryggen-wrapper">
                <img class="bryggen" src="/illustrations/bryggen.svg" alt="">
            </SystemFlex>
        </SystemFlex>

        <SystemFlex class="water-wrapper">
            <Wave class="water-wave"></Wave>
            <Water :light="{
                x: 0,
                y: 0,
                rotation: 0
            }"></Water>
        </SystemFlex>



        <SystemFlex gap="2vw" class="under-water" align="center">
            <SystemFlex grow="1" gap="2rem" direction="column">
                <SystemH2 class="white">Hvem er vi</SystemH2>

                <SystemP class="white">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</SystemP>
                
                <SystemFlex>
                    <SystemButton border="#ffffff" color="var(--primary)" background="#ffffff">Kom i gang</SystemButton>
                </SystemFlex>
            </SystemFlex>

            <SystemFlex grow="1">
                <video class="video" controls>
                    <source src="/media/mock.mp4" type="video/mp4">
                    Your browser does not support the video tag.
                </video>
            </SystemFlex>
        </SystemFlex>
    </SystemFlex>
</template>

<style scoped lang="scss">
.top-content {
    padding-left: var(--page-padding);

    .left {
        max-width: 40.5rem;
        padding-top: 5rem;
    }
}

.under-water {
    position: relative;
    z-index: 3;

    padding: 0 var(--page-padding);

    padding-top: 350px;

    .video {
        width: 100%;
        height: 100%;

        border-radius: var(--border-radius);
    }
}

.bryggen-wrapper {
    position: relative;

    z-index: -1;

    .bryggen {
        position: absolute;
        right: 0;
    }
}

.water-wrapper {
    position: relative;
    top: 50vh;
}

.white {
    color: #ffffff;
}
</style>