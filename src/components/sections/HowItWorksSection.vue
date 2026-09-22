<template>
  <section id="how" class="py-24 bg-[#0B1220] relative">
    <!-- Decorative background elements -->
    <div class="absolute top-0 left-0 w-full h-px bg-gradient-to-r from-transparent via-white/10 to-transparent"></div>
    <div class="absolute top-1/4 right-0 w-96 h-96 bg-[#22E27A]/5 rounded-full blur-3xl pointer-events-none"></div>

    <div class="container mx-auto px-6 max-w-7xl">
      <RevealOnScroll>
        <SectionHeading subtitle="Your journey to earning from EV charging is simple and straightforward.">
          How It Works
        </SectionHeading>
      </RevealOnScroll>

      <div class="mt-16 relative">
        <!-- Connecting Line for Desktop -->
        <div class="hidden lg:block absolute top-12 left-[4%] right-[4%] h-0.5 bg-white/10 z-0"></div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-10 relative z-10">
          <RevealOnScroll 
            v-for="(step, index) in content.howItWorks" 
            :key="index"
            :delay="index * 100"
          >
            <div class="flex flex-col items-start relative">
              <div class="w-24 h-24 rounded-2xl bg-[#0B1220] border-2 border-[#22E27A] flex items-center justify-center text-3xl font-black text-[#22E27A] mb-8 shadow-[0_0_15px_rgba(34,226,122,0.3)]">
                {{ step.step }}
              </div>
              <h3 class="text-xl font-bold text-white mb-3">{{ step.title }}</h3>
              <p class="text-gray-400 leading-relaxed">{{ step.description }}</p>
            </div>
          </RevealOnScroll>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { siteContent as content } from '../../data/content'
import SectionHeading from '../ui/SectionHeading.vue'
import RevealOnScroll from '../ui/RevealOnScroll.vue'
</script>
