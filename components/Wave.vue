<script setup lang="ts">
const screenSize = useWindowSize()

let lastSize = 3200

const width = computed(() => {
  const newSize = Math.max(
    lastSize * Math.floor((screenSize.width.value * 4) / lastSize), 
    lastSize
  )

  lastSize = newSize

  return newSize
})

const widthStyle = computed(() => {
  return `${width.value}px`
})

const offset = computed(() => {
  return -(lastSize / 4)
})

const offsetStyle = computed(() => {
  return `${offset.value}px`
})

watchEffect(() => {
  console.log(width.value, offset.value)
})
</script>

<template>
    <div class="ocean">
        <div class="wave"></div>
        <div class="wave-2 wave"></div>
        <div class="wave-3 wave"></div>
    </div>
</template>

<style scoped lang="scss">
.ocean {
  position: relative;

  z-index: -1;

  width: 100%;
  height: 200px;
}

.wave {
  background: url(/illustrations/sexy.svg) repeat-x; 
  position: absolute;
  top: -200px;

  width: v-bind(widthStyle);
  animation: wave 10s cubic-bezier( 0.36, 0.45, 0.63, 0.53) infinite;
  height: 200px;
}

.wave-2 {
  top: -220px;

  animation: wave 12s cubic-bezier(0.36, 0.45, 0.63, 0.53) -.125s infinite, scale 7s ease -1.25s infinite, swell 8s ease -1.25s infinite;
  opacity: 0.5;
}

.wave-3 {
  top: -200px;

  animation: wave 9s cubic-bezier(0.36, 0.45, 0.63, 0.53) -.125s infinite, scale 7s ease -1.25s infinite, swell 8s ease -1.25s infinite;
  opacity: 0.2;
}

@keyframes wave {
  0% {
    margin-left: 0;
  }

  100% {
    margin-left: v-bind(offsetStyle);
  }
}

@keyframes scale {
  0% {
    height: 200px;
  }

  100% {
    height: 200px;
  }
}

@keyframes swell {
  0%, 100% {
    transform: translate3d(0,-0px,0);
  }
  50% {
    transform: translate3d(0,5px,0);
  }
}
</style>