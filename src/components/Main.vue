<script setup>
import { Graphics } from 'pixi.js'
import { computed, ref } from 'vue'
import { useScreen } from 'vue3-pixi'

const screen = useScreen()

const scale = computed(() => {
  const { width, height } = screen.value
  return Math.min(width / 640, height / 480)
})
const position = computed(() => {
  const { width, height } = screen.value
  return {
    x: 0,
    y: 0,
  }
})

const mask = ref<Graphics>()

function drawMask(mask: Graphics) {
  mask.beginFill(0xFF0000, 0.5).drawRect(0, 0, 900, 480).endFill()
}
</script>

<template>
  <container :x="position.x" :y="position.y" :scale="scale">
    <graphics ref="mask" is-mask @draw="drawMask" />
    <container :mask="mask">
      <slot />
    </container>
  </container>
</template>

<style lang="scss" scoped></style>
