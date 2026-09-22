<template>
  <div class="border-b border-white/10 overflow-hidden">
    <button 
      @click="isOpen = !isOpen"
      class="w-full flex items-center justify-between py-5 text-left focus:outline-none focus-visible:ring-2 focus-visible:ring-[#22E27A] rounded-lg px-2"
    >
      <span class="text-lg font-medium" :class="isOpen ? 'text-[#22E27A]' : 'text-white'">{{ question }}</span>
      <ChevronDown 
        class="w-5 h-5 text-gray-400 transition-transform duration-300" 
        :class="isOpen ? 'rotate-180 text-[#22E27A]' : ''"
      />
    </button>
    <div 
      class="overflow-hidden transition-all duration-300 ease-in-out"
      :style="{ maxHeight: isOpen ? contentHeight + 'px' : '0px' }"
    >
      <div ref="contentElement" class="pb-5 px-2 text-gray-400 leading-relaxed">
        {{ answer }}
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, nextTick, watch } from 'vue'
import { ChevronDown } from '@lucide/vue'

const props = defineProps({
  question: { type: String, required: true },
  answer: { type: String, required: true }
})

const isOpen = ref(false)
const contentElement = ref(null)
const contentHeight = ref(0)

const calculateHeight = () => {
  if (contentElement.value) {
    contentHeight.value = contentElement.value.scrollHeight
  }
}

watch(isOpen, async (newVal) => {
  if (newVal) {
    await nextTick()
    calculateHeight()
  }
})

onMounted(() => {
  // Setup listener for window resize to recalculate height if open
  window.addEventListener('resize', () => {
    if (isOpen.value) {
      calculateHeight()
    }
  })
})
</script>
