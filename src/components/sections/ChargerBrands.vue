<template>
  <section class="py-16 bg-[#080d17] border-y border-white/5 overflow-hidden">
    <div class="container mx-auto px-6 max-w-7xl mb-8">
      <h3 class="text-center text-gray-500 font-medium uppercase tracking-widest text-sm">
        Trusted Chargers From Leading Brands
      </h3>
    </div>
    
    <!-- Infinite Marquee -->
    <div class="relative w-full flex overflow-x-hidden group">
      <!-- Gradient masks for smooth edges -->
      <div class="absolute top-0 left-0 w-32 h-full bg-gradient-to-r from-[#080d17] to-transparent z-10"></div>
      <div class="absolute top-0 right-0 w-32 h-full bg-gradient-to-l from-[#080d17] to-transparent z-10"></div>
      
      <div class="flex animate-marquee group-hover:[animation-play-state:paused] whitespace-nowrap">
        <!-- Duplicate content twice for seamless loop -->
        <div class="flex items-center gap-12 px-6" v-for="n in 2" :key="n">
          <div 
            v-for="(brand, i) in content.brands" 
            :key="i"
            class="h-20 w-48 bg-white/5 border border-white/10 rounded-xl flex items-center justify-center filter grayscale hover:grayscale-0 hover:bg-white/10 transition-all duration-300 mx-2"
          >
            <!-- In a real app, replace this text with brand logo images -->
            <span class="text-xl font-bold text-gray-400 font-sans tracking-wide">
              {{ brand }}
            </span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { siteContent as content } from '../../data/content'
</script>
