<template>
  <section id="calculator" class="py-24 bg-gradient-dark">
    <div class="container mx-auto px-6 max-w-7xl">
      <div class="flex flex-col lg:flex-row items-center gap-16">
        
        <!-- Calculator Inputs -->
        <div class="w-full lg:w-1/2">
          <RevealOnScroll>
            <SectionHeading>
              {{ content.calculator.title }}
            </SectionHeading>
            
            <div class="bg-white/5 border border-white/10 rounded-2xl p-8 mt-8">
              <!-- Number of Chargers -->
              <div class="mb-8">
                <label class="block text-white font-medium mb-4 flex justify-between">
                  <span>Number of Chargers</span>
                  <span class="text-[#22E27A] font-bold">{{ chargers }}</span>
                </label>
                <input 
                  type="range" 
                  min="1" max="10" 
                  v-model.number="chargers"
                  class="w-full accent-[#22E27A] h-2 bg-white/10 rounded-lg appearance-none cursor-pointer"
                >
              </div>

              <!-- Charger Type -->
              <div class="mb-8">
                <label class="block text-white font-medium mb-4">Charger Type</label>
                <div class="relative">
                  <select 
                    v-model="selectedType" 
                    class="w-full bg-[#0B1220] border border-white/20 text-white rounded-xl px-4 py-3 appearance-none focus:outline-none focus:border-[#22E27A] transition-colors"
                  >
                    <option v-for="(type, i) in content.calculator.chargerTypes" :key="i" :value="type">
                      {{ type.label }}
                    </option>
                  </select>
                  <ChevronDown class="absolute right-4 top-1/2 -translate-y-1/2 w-5 h-5 text-gray-400 pointer-events-none" />
                </div>
              </div>

              <!-- Daily Usage (Hours) -->
              <div class="mb-8">
                <label class="block text-white font-medium mb-4 flex justify-between">
                  <span>Average Daily Usage (Hours)</span>
                  <span class="text-[#22E27A] font-bold">{{ hoursPerDay }} hrs</span>
                </label>
                <input 
                  type="range" 
                  min="1" max="24" step="0.5"
                  v-model.number="hoursPerDay"
                  class="w-full accent-[#22E27A] h-2 bg-white/10 rounded-lg appearance-none cursor-pointer"
                >
              </div>

              <!-- Profit per kWh -->
              <div>
                <label class="block text-white font-medium mb-4 flex justify-between">
                  <span>Your Profit Margin (₹ per kWh)</span>
                  <span class="text-[#22E27A] font-bold">₹{{ profitPerKwh }}</span>
                </label>
                <input 
                  type="range" 
                  min="1" max="10" step="0.5"
                  v-model.number="profitPerKwh"
                  class="w-full accent-[#22E27A] h-2 bg-white/10 rounded-lg appearance-none cursor-pointer"
                >
              </div>
            </div>
          </RevealOnScroll>
        </div>

        <!-- Calculator Results -->
        <div class="w-full lg:w-1/2">
          <RevealOnScroll delay="200">
            <div class="relative">
              <!-- Decorative elements -->
              <div class="absolute -inset-1 bg-gradient-to-r from-[#22E27A] to-blue-500 rounded-3xl blur opacity-20"></div>
              
              <div class="relative bg-[#0B1220] border border-white/10 rounded-2xl p-10 overflow-hidden text-center">
                <div class="absolute top-0 left-0 w-full h-1 bg-gradient-to-r from-[#22E27A] to-transparent"></div>
                
                <h3 class="text-xl text-gray-400 font-medium mb-2">Estimated Monthly Earnings</h3>
                <div class="text-5xl md:text-7xl font-bold text-white mb-8">
                  ₹{{ formatNumber(monthlyEarnings) }}
                </div>
                
                <div class="h-px w-full bg-white/10 mb-8"></div>
                
                <h3 class="text-lg text-gray-400 font-medium mb-2">Estimated Annual Earnings</h3>
                <div class="text-3xl md:text-4xl font-bold text-[#22E27A] mb-8">
                  ₹{{ formatNumber(annualEarnings) }}
                </div>
                
                <p class="text-sm text-gray-500 italic mt-6">
                  {{ content.calculator.disclaimer }}
                </p>
              </div>
            </div>
          </RevealOnScroll>
        </div>
        
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, computed } from 'vue'
import { ChevronDown } from '@lucide/vue'
import { siteContent as content } from '../../data/content'
import SectionHeading from '../ui/SectionHeading.vue'
import RevealOnScroll from '../ui/RevealOnScroll.vue'

const chargers = ref(2)
const selectedType = ref(content.calculator.chargerTypes[0]) // Default AC - 7.4 kW
const hoursPerDay = ref(4)
const profitPerKwh = ref(3)

const dailyEarnings = computed(() => {
  const kW = selectedType.value.value
  const kWhPerDay = kW * hoursPerDay.value * chargers.value
  return kWhPerDay * profitPerKwh.value
})

const monthlyEarnings = computed(() => dailyEarnings.value * 30)
const annualEarnings = computed(() => dailyEarnings.value * 365)

const formatNumber = (num) => {
  return Math.round(num).toLocaleString('en-IN')
}
</script>
