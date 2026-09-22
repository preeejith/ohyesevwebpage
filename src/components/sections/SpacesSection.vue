<template>
  <section id="spaces" class="py-24 bg-gradient-dark">
    <div class="container mx-auto px-6 max-w-7xl">
      <RevealOnScroll>
        <SectionHeading centered subtitle="Our EV charging solutions are tailored for various property types.">
          Perfect For <span class="text-white">Every Space</span>
        </SectionHeading>
      </RevealOnScroll>

      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6 mt-16">
        <RevealOnScroll 
          v-for="(space, index) in content.spaces" 
          :key="index"
          :delay="index * 100"
        >
          <div class="group relative overflow-hidden rounded-2xl bg-white/5 border border-white/10 p-8 hover:-translate-y-2 transition-transform duration-300">
            <!-- Glow background on hover -->
            <div class="absolute inset-0 bg-gradient-to-br from-[#22E27A]/20 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300 pointer-events-none"></div>
            
            <div class="relative z-10">
              <component :is="icons[space.icon]" class="w-12 h-12 text-[#22E27A] mb-6" />
              <h3 class="text-2xl font-bold text-white mb-3">{{ space.title }}</h3>
              <p class="text-gray-400 leading-relaxed">{{ space.benefit }}</p>
            </div>
          </div>
        </RevealOnScroll>
      </div>
    </div>
  </section>
</template>

<script setup>
import { Building, Home, Hotel, CarFront } from '@lucide/vue'
import { siteContent as content } from '../../data/content'
import SectionHeading from '../ui/SectionHeading.vue'
import RevealOnScroll from '../ui/RevealOnScroll.vue'

const icons = {
  Building,
  Home,
  Hotel,
  CarFront
}
</script>
