<template>
  <div class="text-center p-6 rounded-2xl bg-white/5 border border-white/10 backdrop-blur-sm">
    <div class="text-4xl md:text-5xl font-bold text-white mb-2 flex justify-center items-center">
      <span ref="counterElement">{{ displayValue }}</span>
      <span class="text-[#22E27A]">{{ suffix }}</span>
    </div>
    <div class="text-gray-400 font-medium uppercase tracking-wider text-sm">{{ label }}</div>
  </div>
</template>

<script setup>
import { ref, watch, onMounted } from 'vue'
import { useIntersectionObserver } from '@vueuse/core'

const props = defineProps({
  value: { type: Number, required: true },
  label: { type: String, required: true },
  suffix: { type: String, default: '' },
  duration: { type: Number, default: 2000 }
})

const counterElement = ref(null)
const displayValue = ref(0)
const hasAnimated = ref(false)

const animateCounter = () => {
  let startTimestamp = null
  const step = (timestamp) => {
    if (!startTimestamp) startTimestamp = timestamp
    const progress = Math.min((timestamp - startTimestamp) / props.duration, 1)
    
    // easeOutExpo
    const easeProgress = progress === 1 ? 1 : 1 - Math.pow(2, -10 * progress)
    
    // If value is a float, keep it float, else int
    const isFloat = props.value % 1 !== 0
    let current = easeProgress * props.value
    
    if (isFloat) {
      displayValue.value = current.toFixed(1)
    } else {
      displayValue.value = Math.floor(current)
    }
    
    if (progress < 1) {
      window.requestAnimationFrame(step)
    } else {
      displayValue.value = props.value
    }
  }
  window.requestAnimationFrame(step)
}

onMounted(() => {
  useIntersectionObserver(
    counterElement,
    ([{ isIntersecting }]) => {
      if (isIntersecting && !hasAnimated.value) {
        hasAnimated.value = true
        animateCounter()
      }
    },
    { threshold: 0.5 }
  )
})
</script>
