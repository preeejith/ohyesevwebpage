<template>
  <div class="min-h-screen bg-[#0B1220] text-white">
    <TheNavbar />
    
    <main>
      <HeroSection />
      <StatsBar />
      <WhyEarnSection />
      <SpacesSection />
      <HowItWorksSection />
      <EarningsCalculator />
      <PartnerModels />
      <ChargerBrands />
      <AppDownloadSection />
      <FaqSection />
      <CtaSection />
    </main>

    <TheFooter />
    <WhatsAppFloat />
  </div>
</template>

<script setup>
import TheNavbar from './components/layout/TheNavbar.vue'
import TheFooter from './components/layout/TheFooter.vue'
import WhatsAppFloat from './components/layout/WhatsAppFloat.vue'

import HeroSection from './components/sections/HeroSection.vue'
import StatsBar from './components/sections/StatsBar.vue'
import WhyEarnSection from './components/sections/WhyEarnSection.vue'
import SpacesSection from './components/sections/SpacesSection.vue'
import HowItWorksSection from './components/sections/HowItWorksSection.vue'
import EarningsCalculator from './components/sections/EarningsCalculator.vue'
import PartnerModels from './components/sections/PartnerModels.vue'
import ChargerBrands from './components/sections/ChargerBrands.vue'
import AppDownloadSection from './components/sections/AppDownloadSection.vue'
import FaqSection from './components/sections/FaqSection.vue'
import CtaSection from './components/sections/CtaSection.vue'
</script>
