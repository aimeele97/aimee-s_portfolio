<template>
  <component :is="component" :class="classes">
    <router-link
      v-if="href"
      :to="href"
      aria-hidden="true"
      class="text-decoration-none text-end text-md-start d-none d-sm-inline-block"
      style="user-select: none"
    >
      <span class="text-primary">#</span>
    </router-link>

    <slot>
      {{ content }}
    </slot>
  </component>
</template>

<script setup lang="ts">
import { computed } from 'vue'

type HeadingLevel = '1' | '2' | '3' | '4' | '5'
const HEADING_CLASSES = {
  1: 'text-h3 text-sm-h3',
  2: 'text-h4 text-sm-h4',
  3: 'text-h5',
  4: 'text-h6',
  5: 'text-subtitle-1 font-weight-medium',
}

const props = defineProps<{
  content: string
  href: string
  level: HeadingLevel
}>()

const component = computed(() => `h${props.level}`)
const classes = computed(() => ['v-heading', 'my-2', HEADING_CLASSES[props.level]])
</script>

<style lang="sass">
.v-heading
  display: block
  position: relative

  > a
    bottom: 0
    font-size: .75em
    left: 0
    margin: 0 -.7em
    position: absolute
    right: 0
    top: 0

    &:not(:hover):not(:focus)
      opacity: 0
</style>
