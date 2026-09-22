<template>
  <div class="mb-12" :class="alignmentClass">
    <h2 class="text-3xl md:text-5xl font-bold mb-4">
      <slot></slot>
    </h2>
    <div v-if="subtitle" class="text-gray-400 text-lg max-w-2xl" :class="subtitleAlignmentClass">
      {{ subtitle }}
    </div>
  </div>
</template>

<script setup>
import { computed } from 'vue'

const props = defineProps({
  subtitle: {
    type: String,
    default: ''
  },
  centered: {
    type: Boolean,
    default: false
  }
})

const alignmentClass = computed(() => props.centered ? 'text-center' : 'text-left')
const subtitleAlignmentClass = computed(() => props.centered ? 'mx-auto' : '')
</script>
