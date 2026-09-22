<template>
  <section class="py-24 bg-[#0B1220] overflow-hidden">
    <div class="container mx-auto px-6 max-w-7xl relative">
      <!-- Glow effect -->
      <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[800px] h-[800px] bg-[#22E27A]/10 rounded-full blur-[100px] pointer-events-none"></div>

      <div class="flex flex-col md:flex-row items-center justify-between gap-12 bg-gradient-to-br from-white/10 to-white/5 border border-white/10 rounded-3xl p-8 md:p-16 relative z-10">
        
        <div class="w-full md:w-1/2">
          <RevealOnScroll>
            <h2 class="text-4xl md:text-5xl font-bold mb-6 text-white">
              Manage Everything <br/>
              <span class="text-[#22E27A]">In The Oh Yes App</span>
            </h2>
            <p class="text-xl text-gray-300 mb-8 max-w-lg">
              Track earnings, monitor usage, set pricing, and get 24/7 support right from your smartphone.
            </p>
            
            <ul class="space-y-4 mb-10">
              <li v-for="(feature, i) in content.appFeatures" :key="i" class="flex items-center gap-3 text-lg text-gray-200">
                <CheckCircle2 class="w-6 h-6 text-[#22E27A]" />
                {{ feature }}
              </li>
            </ul>

            <div class="flex flex-col sm:flex-row gap-4">
              <a href="#" class="inline-flex items-center justify-center gap-3 bg-white text-[#0B1220] px-6 py-3 rounded-xl hover:bg-gray-200 transition-colors font-semibold">
                <Apple class="w-6 h-6" />
                <div class="text-left">
                  <div class="text-[10px] uppercase leading-none mb-1">Download on the</div>
                  <div class="text-sm leading-none">App Store</div>
                </div>
              </a>
              <a href="#" class="inline-flex items-center justify-center gap-3 bg-white text-[#0B1220] px-6 py-3 rounded-xl hover:bg-gray-200 transition-colors font-semibold">
                <Play class="w-6 h-6" />
                <div class="text-left">
                  <div class="text-[10px] uppercase leading-none mb-1">GET IT ON</div>
                  <div class="text-sm leading-none">Google Play</div>
                </div>
              </a>
            </div>
          </RevealOnScroll>
        </div>

        <div class="w-full md:w-1/2 flex justify-center relative">
          <RevealOnScroll delay="200" class="w-full flex justify-center relative">
            <!-- Abstract Phone Mockup -->
            <div class="relative w-64 h-[500px] bg-[#080d17] rounded-[40px] border-[8px] border-gray-800 shadow-2xl overflow-hidden flex flex-col z-10">
              <!-- Notch -->
              <div class="absolute top-0 left-1/2 -translate-x-1/2 w-32 h-6 bg-gray-800 rounded-b-2xl z-20"></div>
              
              <!-- Mock UI -->
              <div class="flex-1 bg-[#0B1220] p-6 flex flex-col pt-12">
                <div class="text-center mb-6">
                  <div class="text-sm text-gray-400">Today's Earnings</div>
                  <div class="text-3xl font-bold text-white mt-1">₹1,240</div>
                </div>
                
                <!-- Chart placeholder -->
                <div class="h-32 bg-white/5 rounded-xl mb-6 border border-white/10 flex items-end px-4 gap-2 pb-2">
                  <div class="w-1/5 bg-[#22E27A]/30 h-[40%] rounded-t-sm relative"><div class="absolute bottom-0 w-full bg-[#22E27A] h-[2px]"></div></div>
                  <div class="w-1/5 bg-[#22E27A]/30 h-[60%] rounded-t-sm relative"><div class="absolute bottom-0 w-full bg-[#22E27A] h-[2px]"></div></div>
                  <div class="w-1/5 bg-[#22E27A]/30 h-[30%] rounded-t-sm relative"><div class="absolute bottom-0 w-full bg-[#22E27A] h-[2px]"></div></div>
                  <div class="w-1/5 bg-[#22E27A]/30 h-[80%] rounded-t-sm relative"><div class="absolute bottom-0 w-full bg-[#22E27A] h-[2px]"></div></div>
                  <div class="w-1/5 bg-[#22E27A]/50 h-[100%] rounded-t-sm relative"><div class="absolute bottom-0 w-full bg-[#22E27A] h-[2px] glow-effect"></div></div>
                </div>
                
                <div class="space-y-3">
                  <div class="h-16 bg-white/5 rounded-xl border border-white/10 p-3 flex justify-between items-center">
                    <div class="flex gap-3 items-center">
                      <div class="w-10 h-10 rounded-full bg-[#22E27A]/20 flex items-center justify-center">
                        <Zap class="w-5 h-5 text-[#22E27A]" />
                      </div>
                      <div>
                        <div class="text-sm font-semibold text-white">Station 1</div>
                        <div class="text-xs text-[#22E27A]">Charging</div>
                      </div>
                    </div>
                    <div class="text-right">
                      <div class="text-sm font-bold text-white">12.4 kWh</div>
                      <div class="text-xs text-gray-400">₹186</div>
                    </div>
                  </div>
                  <div class="h-16 bg-white/5 rounded-xl border border-white/10 p-3 flex justify-between items-center">
                    <div class="flex gap-3 items-center">
                      <div class="w-10 h-10 rounded-full bg-gray-800 flex items-center justify-center">
                        <Check class="w-5 h-5 text-gray-400" />
                      </div>
                      <div>
                        <div class="text-sm font-semibold text-white">Station 2</div>
                        <div class="text-xs text-gray-400">Available</div>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
            
            <!-- Decorative circles behind phone -->
            <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-80 h-80 border border-[#22E27A]/20 rounded-full z-0"></div>
            <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[400px] h-[400px] border border-white/5 rounded-full z-0"></div>
          </RevealOnScroll>
        </div>

      </div>
    </div>
  </section>
</template>

<script setup>
import { CheckCircle2, Apple, Play, Zap, Check } from '@lucide/vue'
import { siteContent as content } from '../../data/content'
import RevealOnScroll from '../ui/RevealOnScroll.vue'
</script>
