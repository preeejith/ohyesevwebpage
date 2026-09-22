<template>
  <section id="faq" class="py-24 bg-gradient-dark">
    <div class="container mx-auto px-6 max-w-3xl">
      <RevealOnScroll>
        <SectionHeading centered>
          Frequently Asked <span class="text-[#22E27A]">Questions</span>
        </SectionHeading>
      </RevealOnScroll>

      <div class="mt-16">
        <RevealOnScroll>
          <div class="bg-white/5 border border-white/10 rounded-2xl p-4 md:p-8">
            <FaqItem 
              v-for="(faq, index) in content.faqs" 
              :key="index"
              :question="faq.q"
              :answer="faq.a"
              :class="{ 'border-none': index === content.faqs.length - 1 }"
            />
          </div>
        </RevealOnScroll>
      </div>
    </div>
  </section>
</template>

<script setup>
import { siteContent as content } from '../../data/content'
import SectionHeading from '../ui/SectionHeading.vue'
import FaqItem from '../ui/FaqItem.vue'
import RevealOnScroll from '../ui/RevealOnScroll.vue'
</script>
