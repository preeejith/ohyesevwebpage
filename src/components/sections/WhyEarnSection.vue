<template>
  <section class="py-24 bg-[#0B1220]">
    <div class="container mx-auto px-6 max-w-7xl">
      <RevealOnScroll>
        <SectionHeading centered subtitle="Join the EV revolution and maximize the potential of your property.">
          Why Partner with <span class="text-[#22E27A]">Oh Yes</span>?
        </SectionHeading>
      </RevealOnScroll>

      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8 mt-16">
        <RevealOnScroll 
          v-for="(card, index) in content.whyEarn" 
          :key="index"
          :delay="index * 100"
        >
          <div class="bg-white/5 border border-white/10 rounded-2xl p-8 h-full hover:bg-white/10 transition-colors duration-300 group">
            <div class="w-14 h-14 rounded-full bg-[#22E27A]/20 flex items-center justify-center mb-6 text-[#22E27A] group-hover:scale-110 group-hover:bg-[#22E27A] group-hover:text-[#0B1220] transition-all duration-300">
              <component :is="icons[card.icon]" class="w-7 h-7" />
            </div>
            <h3 class="text-xl font-bold text-white mb-3">{{ card.title }}</h3>
            <p class="text-gray-400 leading-relaxed">{{ card.description }}</p>
          </div>
        </RevealOnScroll>
      </div>
    </div>
  </section>
</template>

<script setup>
import { CircleDollarSign, Wrench, ShieldCheck, Smartphone } from '@lucide/vue'
import { siteContent as content } from '../../data/content'
import SectionHeading from '../ui/SectionHeading.vue'
import RevealOnScroll from '../ui/RevealOnScroll.vue'

const icons = {
  CircleDollarSign,
  Wrench,
  ShieldCheck,
  Smartphone
}
</script>
