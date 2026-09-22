<template>
  <div 
    ref="target" 
    class="transition-all duration-1000 ease-out"
    :class="[
      isVisible ? 'opacity-100 translate-y-0' : 'opacity-0 translate-y-12',
      delayClass
    ]"
  >
    <slot></slot>
  </div>
</template>

<script setup>
import { ref, onMounted, computed } from 'vue'
import { useIntersectionObserver } from '@vueuse/core'

const props = defineProps({
  delay: {
    type: Number,
    default: 0
  }
})

const target = ref(null)
const isVisible = ref(false)

const delayClass = computed(() => {
  if (props.delay === 100) return 'delay-100'
  if (props.delay === 200) return 'delay-200'
  if (props.delay === 300) return 'delay-300'
  if (props.delay === 400) return 'delay-400'
  if (props.delay === 500) return 'delay-500'
  if (props.delay === 700) return 'delay-700'
  return ''
})

onMounted(() => {
  // Check prefers-reduced-motion
  const prefersReducedMotion = window.matchMedia('(prefers-reduced-motion: reduce)').matches
  if (prefersReducedMotion) {
    isVisible.value = true
    return
  }

  useIntersectionObserver(
    target,
    ([{ isIntersecting }]) => {
      if (isIntersecting && !isVisible.value) {
        isVisible.value = true
      }
    },
    { threshold: 0.1, rootMargin: '0px 0px -50px 0px' }
  )
})
</script>
