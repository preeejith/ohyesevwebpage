<template>
  <section id="models" class="py-24 bg-[#0B1220]">
    <div class="container mx-auto px-6 max-w-7xl">
      <RevealOnScroll>
        <SectionHeading centered subtitle="Choose the business model that best fits your investment appetite.">
          Flexible <span class="text-white">Partner Models</span>
        </SectionHeading>
      </RevealOnScroll>

      <div class="grid grid-cols-1 md:grid-cols-3 gap-8 mt-16">
        <RevealOnScroll 
          v-for="(model, index) in content.partnerModels" 
          :key="index"
          :delay="index * 100"
        >
          <div 
            class="relative h-full p-8 rounded-3xl transition-all duration-300"
            :class="[
              model.highlight 
                ? 'bg-[#22E27A] text-[#0B1220] shadow-[0_10px_30px_rgba(34,226,122,0.3)] hover:-translate-y-2' 
                : 'bg-white/5 border border-white/10 text-white hover:bg-white/10 hover:-translate-y-2'
            ]"
          >
            <div 
              class="w-16 h-16 rounded-full flex items-center justify-center mb-8"
              :class="model.highlight ? 'bg-[#0B1220]/10 text-[#0B1220]' : 'bg-[#22E27A]/20 text-[#22E27A]'"
            >
              <Briefcase class="w-8 h-8" v-if="index === 0" />
              <PieChart class="w-8 h-8" v-else-if="index === 1" />
              <Handshake class="w-8 h-8" v-else />
            </div>
            
            <h3 class="text-2xl font-bold mb-4">{{ model.title }}</h3>
            <p :class="model.highlight ? 'text-[#0B1220]/80' : 'text-gray-400'" class="leading-relaxed mb-8">
              {{ model.description }}
            </p>
            
            <div class="mt-auto">
              <BaseButton 
                :variant="model.highlight ? 'outline' : 'white'" 
                class="w-full"
                :class="model.highlight ? '!border-[#0B1220] !text-[#0B1220] hover:!bg-[#0B1220] hover:!text-[#22E27A]' : ''"
                @click="scrollTo('#contact')"
              >
                Inquire Now
              </BaseButton>
            </div>
          </div>
        </RevealOnScroll>
      </div>
    </div>
  </section>
</template>

<script setup>
import { Briefcase, PieChart, Handshake } from '@lucide/vue'
import { siteContent as content } from '../../data/content'
import SectionHeading from '../ui/SectionHeading.vue'
import RevealOnScroll from '../ui/RevealOnScroll.vue'
import BaseButton from '../ui/BaseButton.vue'

const scrollTo = (selector) => {
  const el = document.querySelector(selector)
  if (el) {
    const offset = 80
    const top = el.getBoundingClientRect().top + window.scrollY - offset
    window.scrollTo({ top, behavior: 'smooth' })
  }
}
</script>
