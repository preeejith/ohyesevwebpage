<template>
  <section id="infrastructure" class="py-24 bg-[#0B1220] relative overflow-hidden">
    <!-- Background glow for orange theme -->
    <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-full max-w-4xl h-96 bg-[#F97316]/5 blur-3xl rounded-full pointer-events-none"></div>

    <div class="container mx-auto px-6 max-w-7xl relative z-10">
      <RevealOnScroll>
        <SectionHeading centered subtitle="Powering Your Station. Supporting Your Business. Growing Your Network.">
          Complete <span class="text-[#F97316]">EV Infrastructure</span>
        </SectionHeading>
      </RevealOnScroll>

      <!-- 1 & 2: Solutions & Infrastructure -->
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 mt-16">
        <RevealOnScroll :delay="100">
          <div class="bg-white/5 border border-[#F97316]/20 rounded-3xl p-8 h-full hover:bg-white/10 transition-colors group">
            <div class="w-14 h-14 rounded-full bg-[#F97316]/10 flex items-center justify-center mb-6 text-[#F97316] group-hover:scale-110 group-hover:bg-[#F97316] group-hover:text-[#0B1220] transition-all duration-300">
              <Zap class="w-7 h-7" />
            </div>
            <h3 class="text-2xl font-bold text-white mb-4">1. EV CHARGING SOLUTIONS</h3>
            <p class="text-gray-400 mb-6">Oh Yes provides EV charging solutions for residential, commercial and public locations.</p>
            <h4 class="text-lg font-semibold text-white mb-4">Charger Range:</h4>
            <ul class="grid grid-cols-2 gap-3">
              <li v-for="charger in ['AC – 7.4 kW', 'AC – 11 kW', 'AC – 22 kW', 'DC – 30 kW', 'DC – 60 kW', 'DC – 80–120 kW']" :key="charger" class="flex items-center text-gray-300">
                <CheckCircle2 class="w-4 h-4 text-[#F97316] mr-2" />
                {{ charger }}
              </li>
            </ul>
          </div>
        </RevealOnScroll>

        <RevealOnScroll :delay="200">
          <div class="bg-white/5 border border-[#F97316]/20 rounded-3xl p-8 h-full hover:bg-white/10 transition-colors group">
            <div class="w-14 h-14 rounded-full bg-[#F97316]/10 flex items-center justify-center mb-6 text-[#F97316] group-hover:scale-110 group-hover:bg-[#F97316] group-hover:text-[#0B1220] transition-all duration-300">
              <Settings class="w-7 h-7" />
            </div>
            <h3 class="text-2xl font-bold text-white mb-4">2. COMPLETE EV CHARGING INFRASTRUCTURE</h3>
            <ul class="grid grid-cols-2 gap-y-3 gap-x-6">
              <li v-for="service in ['EV Charger Installation', 'Canopy / Structure', 'Civil Works', 'Foundation', 'Flooring', 'Billboard / Oh Yes Branding', 'Electrical Panels', 'Cables', 'Metering', 'Protection Systems', 'Testing & Commissioning', 'Installation & Connection', 'Technical Support']" :key="service" class="flex items-start text-gray-300">
                <CheckCircle2 class="w-4 h-4 text-[#F97316] mr-2 mt-1 shrink-0" />
                <span class="text-sm">{{ service }}</span>
              </li>
            </ul>
          </div>
        </RevealOnScroll>
      </div>

      <!-- 3 & 4: Canopy & Electrical -->
      <div class="grid grid-cols-1 md:grid-cols-2 gap-8 mt-8">
        <RevealOnScroll :delay="100">
          <div class="bg-[#F97316]/5 border border-[#F97316]/30 rounded-3xl p-8 h-full">
            <h3 class="text-xl font-bold text-white mb-3">3. CANOPY & CIVIL WORKS</h3>
            <p class="text-gray-400 mb-6 text-sm">A complete site infrastructure solution for a durable, modern and weather-protected EV charging station.</p>
            <h4 class="text-white font-medium mb-3 text-sm">Suitable for:</h4>
            <div class="flex flex-wrap gap-2">
              <span v-for="item in ['Highways', 'Hotels', 'Apartments', 'Resorts', 'Commercial Spaces']" :key="item" class="px-3 py-1 bg-white/10 rounded-full text-xs text-gray-300 border border-white/5">
                {{ item }}
              </span>
            </div>
          </div>
        </RevealOnScroll>

        <RevealOnScroll :delay="200">
          <div class="bg-[#F97316]/5 border border-[#F97316]/30 rounded-3xl p-8 h-full">
            <h3 class="text-xl font-bold text-white mb-3">4. ELECTRICAL INFRASTRUCTURE</h3>
            <p class="text-gray-400 mb-4 text-sm">Complete electrical setup for a safe, reliable and efficient EV charging station.</p>
            <ul class="grid grid-cols-2 gap-2">
              <li v-for="item in ['Cables', 'Panels', 'Metering', 'Protection Systems', 'Testing & Commissioning', 'Installation & Connection', 'Approvals & Charges']" :key="item" class="flex items-center text-gray-300 text-xs">
                <ArrowRight class="w-3 h-3 text-[#F97316] mr-2 shrink-0" />
                {{ item }}
              </li>
            </ul>
          </div>
        </RevealOnScroll>
      </div>

      <!-- 5 & 6: Transformer & Deposit -->
      <div class="grid grid-cols-1 md:grid-cols-2 gap-8 mt-8">
        <RevealOnScroll :delay="100">
          <div class="bg-white/5 border border-white/10 rounded-2xl p-6 h-full">
            <div class="flex items-center mb-4">
              <AlertTriangle class="w-6 h-6 text-[#F97316] mr-3" />
              <h3 class="text-lg font-bold text-white">5. TRANSFORMER</h3>
            </div>
            <p class="text-gray-400 text-sm mb-2">Required only when additional capacity is necessary for the EV charging station.</p>
            <p class="text-gray-500 text-xs italic">Cost and installation will be considered separately based on site requirements and KSEB approval.</p>
          </div>
        </RevealOnScroll>
        <RevealOnScroll :delay="200">
          <div class="bg-white/5 border border-white/10 rounded-2xl p-6 h-full">
            <div class="flex items-center mb-4">
              <Shield class="w-6 h-6 text-[#F97316] mr-3" />
              <h3 class="text-lg font-bold text-white">6. KSEB SECURITY DEPOSIT</h3>
            </div>
            <p class="text-gray-400 text-sm mb-2">A security deposit is required for the electrical connection and sanctioned load, as applicable under KSEB regulations.</p>
            <p class="text-white font-semibold text-sm">Amount: <span class="text-[#F97316] font-normal">As applicable based on sanctioned load and site requirements.</span></p>
          </div>
        </RevealOnScroll>
      </div>

      <!-- 7: Installation Process -->
      <div class="mt-20">
        <RevealOnScroll>
          <h3 class="text-2xl font-bold text-center text-white mb-10">7. INSTALLATION PROCESS</h3>
        </RevealOnScroll>
        <div class="grid grid-cols-2 md:grid-cols-4 gap-4">
          <RevealOnScroll v-for="(step, index) in ['Site Assessment', 'Solution Design', 'Installation & Setup', 'Ongoing Support']" :key="index" :delay="index * 100">
            <div class="text-center p-6 border border-[#F97316]/20 rounded-2xl bg-gradient-to-b from-[#F97316]/10 to-transparent h-full flex flex-col justify-center">
              <div class="text-4xl font-black text-[#F97316]/20 mb-3">0{{ index + 1 }}</div>
              <div class="font-semibold text-white">{{ step }}</div>
            </div>
          </RevealOnScroll>
        </div>
      </div>

      <!-- 8 & 9: Benefits & CTA -->
      <div class="mt-20 bg-gradient-to-br from-[#F97316]/20 to-transparent border border-[#F97316]/30 rounded-3xl p-10 lg:p-16 flex flex-col lg:flex-row items-center gap-12 relative overflow-hidden">
        <div class="absolute right-0 top-0 w-64 h-64 bg-[#F97316]/10 rounded-full blur-3xl translate-x-1/2 -translate-y-1/2"></div>
        <div class="flex-1 relative z-10">
          <RevealOnScroll>
            <h3 class="text-2xl font-bold text-white mb-6">8. BUSINESS BENEFITS</h3>
            <ul class="space-y-4">
              <li v-for="benefit in ['Get Discovered', 'Grow Your Customer Base', 'Generate Additional Income', 'Reliable Technical Support', 'One Platform, Multiple Services', 'Be Future Ready']" :key="benefit" class="flex items-center text-lg text-white">
                <div class="w-8 h-8 rounded-full bg-[#F97316]/20 flex items-center justify-center mr-4 shrink-0">
                  <Star class="w-4 h-4 text-[#F97316]" />
                </div>
                {{ benefit }}
              </li>
            </ul>
          </RevealOnScroll>
        </div>
        <div class="flex-1 text-center lg:text-left relative z-10">
          <RevealOnScroll :delay="200">
            <h3 class="text-3xl font-bold text-white mb-6">9. PARTNER WITH OH YES</h3>
            <p class="text-xl text-gray-300 italic mb-8 border-l-4 border-[#F97316] pl-6 py-2">
              “Powering Your Station. Supporting Your Business. Growing Your Network.”
            </p>
            <BaseButton variant="outline" class="!border-[#F97316] !text-[#F97316] hover:!bg-[#F97316] hover:!text-[#0B1220] w-full sm:w-auto" @click="scrollTo('#contact')">
              Partner with Oh Yes
            </BaseButton>
          </RevealOnScroll>
        </div>
      </div>

    </div>
  </section>
</template>

<script setup>
import { Zap, Settings, CheckCircle2, ArrowRight, AlertTriangle, Shield, Star } from '@lucide/vue'
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
