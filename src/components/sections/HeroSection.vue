<template>
  <section class="relative h-screen min-h-[600px] flex items-center justify-center overflow-hidden">
    <!-- Video Background -->
    <div class="absolute inset-0 z-0 bg-[#0B1220]">
      <video 
        src="/evchargevideo.mp4" 
        autoplay 
        muted 
        loop 
        playsinline 
        class="absolute inset-0 w-full h-full object-cover opacity-60"
        poster="data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='100' height='100' fill='%230B1220'><rect width='100' height='100'/></svg>"
      ></video>
      <div class="absolute inset-0 bg-gradient-to-b from-[#0B1220]/80 via-transparent to-[#0B1220]"></div>
    </div>

    <div class="container mx-auto px-6 max-w-7xl relative z-10 text-center mt-16">
      <RevealOnScroll>
        <div class="inline-block px-4 py-1.5 rounded-full bg-[#22E27A]/20 border border-[#22E27A]/30 text-[#22E27A] text-sm font-semibold mb-6 backdrop-blur-sm">
          {{ content.hero.badge }}
        </div>
      </RevealOnScroll>
      
      <RevealOnScroll :delay="100">
        <h1 class="text-5xl md:text-7xl lg:text-8xl font-extrabold text-white tracking-tight mb-6">
          <span class="block">{{ content.hero.title }}</span>
        </h1>
      </RevealOnScroll>

      <RevealOnScroll :delay="200">
        <p class="text-xl md:text-2xl text-gray-300 max-w-3xl mx-auto mb-4 font-light">
          {{ content.hero.subtitle }}
        </p>
        <p class="text-2xl md:text-3xl text-[#22E27A] font-bold mb-10">
          {{ content.hero.tagline }}
        </p>
      </RevealOnScroll>

      <RevealOnScroll :delay="300">
        <div class="flex flex-col sm:flex-row items-center justify-center gap-4">
          <BaseButton variant="primary" size="lg" class="w-full sm:w-auto" @click="scrollTo('#contact')">
            {{ content.hero.ctaPrimary }}
          </BaseButton>
          <BaseButton variant="white" size="lg" class="w-full sm:w-auto" @click="scrollTo('#contact')">
            {{ content.hero.ctaSecondary }}
          </BaseButton>
        </div>
      </RevealOnScroll>
    </div>

    <!-- Scroll Indicator -->
    <div class="absolute bottom-10 left-1/2 -translate-x-1/2 z-10 animate-bounce cursor-pointer" @click="scrollTo('#stats')">
      <ChevronDown class="w-8 h-8 text-white/70 hover:text-white transition-colors" />
    </div>
  </section>
</template>

<script setup>
import { ChevronDown } from '@lucide/vue'
import { siteContent as content } from '../../data/content'
import BaseButton from '../ui/BaseButton.vue'
import RevealOnScroll from '../ui/RevealOnScroll.vue'

const scrollTo = (selector) => {
  const el = document.querySelector(selector)
  if (el) {
    const offset = 80
    const top = el.getBoundingClientRect().top + window.scrollY - offset
    window.scrollTo({ top, behavior: 'smooth' })
  }
}
</script>
