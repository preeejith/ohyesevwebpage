<template>
  <header 
    class="fixed top-0 left-0 w-full z-50 transition-all duration-300 border-b"
    :class="[
      isScrolled 
        ? 'bg-[#0B1220]/95 backdrop-blur-md py-4 border-white/10 shadow-lg' 
        : 'bg-transparent py-6 border-transparent'
    ]"
  >
    <div class="container mx-auto px-6 max-w-7xl flex items-center justify-between">
      <!-- Logo -->
      <a href="#" class="flex items-center gap-2 z-50" @click.prevent="scrollToTop">
        <span class="text-3xl font-extrabold tracking-tight">
          oh<span class="text-[#22E27A]">yes</span>
        </span>
      </a>

      <!-- Desktop Nav -->
      <nav class="hidden lg:flex items-center gap-8">
        <a 
          v-for="item in navItems" 
          :key="item.name" 
          :href="item.href"
          @click.prevent="scrollTo(item.href)"
          class="text-sm font-medium text-gray-300 hover:text-white transition-colors"
        >
          {{ item.name }}
        </a>
      </nav>

      <!-- Desktop CTA -->
      <div class="hidden lg:block">
        <BaseButton variant="primary" size="sm" @click="scrollTo('#contact')">
          Download App
        </BaseButton>
      </div>

      <!-- Mobile Menu Toggle -->
      <button 
        class="lg:hidden z-50 p-2 -mr-2 text-white focus:outline-none"
        @click="isMobileMenuOpen = !isMobileMenuOpen"
        aria-label="Toggle Menu"
      >
        <Menu v-if="!isMobileMenuOpen" class="w-6 h-6" />
        <X v-else class="w-6 h-6" />
      </button>

      <!-- Mobile Nav -->
      <div 
        class="fixed inset-0 bg-[#0B1220] z-40 flex flex-col items-center justify-center transition-all duration-300 lg:hidden"
        :class="isMobileMenuOpen ? 'opacity-100 visible' : 'opacity-0 invisible pointer-events-none'"
      >
        <nav class="flex flex-col items-center gap-8 w-full px-6">
          <a 
            v-for="item in navItems" 
            :key="item.name" 
            :href="item.href"
            @click.prevent="scrollTo(item.href)"
            class="text-2xl font-medium text-gray-300 hover:text-[#22E27A] transition-colors"
          >
            {{ item.name }}
          </a>
          <BaseButton variant="primary" size="lg" class="w-full mt-4 max-w-sm" @click="scrollTo('#contact')">
            Download App
          </BaseButton>
        </nav>
      </div>
    </div>
  </header>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import { Menu, X } from '@lucide/vue'
import BaseButton from '../ui/BaseButton.vue'

const isScrolled = ref(false)
const isMobileMenuOpen = ref(false)

const navItems = [
  { name: 'Home', href: '#' },
  { name: 'Spaces', href: '#spaces' },
  { name: 'How it works', href: '#how' },
  { name: 'Earnings', href: '#calculator' },
  { name: 'FAQ', href: '#faq' }
]

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50
}

const scrollToTop = () => {
  window.scrollTo({ top: 0, behavior: 'smooth' })
  isMobileMenuOpen.value = false
}

const scrollTo = (selector) => {
  isMobileMenuOpen.value = false
  if (selector === '#') {
    scrollToTop()
    return
  }
  
  const el = document.querySelector(selector)
  if (el) {
    const offset = 80 // Navbar height offset
    const top = el.getBoundingClientRect().top + window.scrollY - offset
    window.scrollTo({ top, behavior: 'smooth' })
  }
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
  // Initial check
  handleScroll()
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>
