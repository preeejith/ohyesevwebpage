<template>
  <section id="stats" class="py-20 relative z-10 -mt-10">
    <div class="container mx-auto px-6 max-w-7xl">
      <RevealOnScroll>
        <div class="grid grid-cols-2 md:grid-cols-4 gap-4 md:gap-8">
          <StatCounter 
            v-for="(stat, index) in content.stats" 
            :key="index"
            :value="stat.value"
            :label="stat.label"
            :suffix="stat.suffix"
          />
        </div>
      </RevealOnScroll>
    </div>
  </section>
</template>

<script setup>
import { siteContent as content } from '../../data/content'
import StatCounter from '../ui/StatCounter.vue'
import RevealOnScroll from '../ui/RevealOnScroll.vue'
</script>
