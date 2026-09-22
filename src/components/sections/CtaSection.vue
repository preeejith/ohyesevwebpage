<template>
  <section id="contact" class="py-24 bg-[#0B1220] relative overflow-hidden">
    <!-- Background pattern -->
    <div class="absolute inset-0 opacity-[0.03] z-0" style="background-image: radial-gradient(#ffffff 1px, transparent 1px); background-size: 32px 32px;"></div>

    <div class="container mx-auto px-6 max-w-5xl relative z-10">
      <div class="bg-gradient-to-br from-[#22E27A]/20 to-[#0B1220] border border-[#22E27A]/30 rounded-3xl p-8 md:p-12 lg:p-16 flex flex-col lg:flex-row gap-12 items-center">
        
        <div class="w-full lg:w-1/2">
          <RevealOnScroll>
            <h2 class="text-3xl md:text-5xl font-bold text-white mb-6 leading-tight">
              Ready to turn your parking space into <span class="text-[#22E27A]">income?</span>
            </h2>
            <p class="text-gray-300 text-lg mb-8 max-w-md">
              Leave your details below and our EV charging experts will contact you for a free site assessment.
            </p>
            
            <div class="flex items-center gap-4 text-white">
              <div class="w-12 h-12 rounded-full bg-white/10 flex items-center justify-center">
                <ShieldCheck class="w-6 h-6 text-[#22E27A]" />
              </div>
              <div>
                <div class="font-bold">100% Secure & Certified</div>
                <div class="text-sm text-gray-400">Leading brands, safe installation</div>
              </div>
            </div>
          </RevealOnScroll>
        </div>

        <div class="w-full lg:w-1/2">
          <RevealOnScroll delay="200">
            <form @submit.prevent="submitForm" class="bg-[#0B1220] p-8 rounded-2xl border border-white/10 shadow-2xl">
              <div class="space-y-5">
                <div>
                  <label for="name" class="block text-sm font-medium text-gray-300 mb-1.5">Full Name</label>
                  <input 
                    type="text" 
                    id="name" 
                    v-model="form.name"
                    required
                    class="w-full bg-white/5 border border-white/10 rounded-xl px-4 py-3 text-white focus:outline-none focus:border-[#22E27A] focus:ring-1 focus:ring-[#22E27A] transition-all"
                    placeholder="John Doe"
                  >
                </div>
                
                <div>
                  <label for="phone" class="block text-sm font-medium text-gray-300 mb-1.5">Phone Number</label>
                  <input 
                    type="tel" 
                    id="phone" 
                    v-model="form.phone"
                    required
                    class="w-full bg-white/5 border border-white/10 rounded-xl px-4 py-3 text-white focus:outline-none focus:border-[#22E27A] focus:ring-1 focus:ring-[#22E27A] transition-all"
                    placeholder="+91 98765 43210"
                  >
                </div>
                
                <div class="grid grid-cols-1 sm:grid-cols-2 gap-5">
                  <div>
                    <label for="city" class="block text-sm font-medium text-gray-300 mb-1.5">City</label>
                    <input 
                      type="text" 
                      id="city" 
                      v-model="form.city"
                      required
                      class="w-full bg-white/5 border border-white/10 rounded-xl px-4 py-3 text-white focus:outline-none focus:border-[#22E27A] focus:ring-1 focus:ring-[#22E27A] transition-all"
                      placeholder="e.g. Mumbai"
                    >
                  </div>
                  
                  <div>
                    <label for="spaceType" class="block text-sm font-medium text-gray-300 mb-1.5">Space Type</label>
                    <div class="relative">
                      <select 
                        id="spaceType"
                        v-model="form.spaceType"
                        required
                        class="w-full bg-[#0B1220] border border-white/10 rounded-xl px-4 py-3 text-white appearance-none focus:outline-none focus:border-[#22E27A] focus:ring-1 focus:ring-[#22E27A] transition-all"
                      >
                        <option value="" disabled selected>Select Type</option>
                        <option value="Apartment">Apartment</option>
                        <option value="Home/Villa">Home / Villa</option>
                        <option value="Hotel/Resort">Hotel / Resort</option>
                        <option value="Commercial">Commercial Parking</option>
                      </select>
                      <ChevronDown class="absolute right-4 top-1/2 -translate-y-1/2 w-5 h-5 text-gray-400 pointer-events-none" />
                    </div>
                  </div>
                </div>
                
                <BaseButton type="submit" variant="primary" class="w-full mt-4 flex justify-center items-center gap-2">
                  <span>Get Free Assessment</span>
                  <ArrowRight class="w-5 h-5" />
                </BaseButton>
              </div>
            </form>
          </RevealOnScroll>
        </div>

      </div>
    </div>
  </section>
</template>

<script setup>
import { reactive } from 'vue'
import { ShieldCheck, ChevronDown, ArrowRight } from '@lucide/vue'
import { siteContent as content } from '../../data/content'
import BaseButton from '../ui/BaseButton.vue'
import RevealOnScroll from '../ui/RevealOnScroll.vue'

const form = reactive({
  name: '',
  phone: '',
  city: '',
  spaceType: ''
})

const submitForm = () => {
  let template = content.whatsapp.messageTemplate
  template = template.replace('{name}', form.name)
  template = template.replace('{phone}', form.phone)
  template = template.replace('{city}', form.city)
  template = template.replace('{spaceType}', form.spaceType)
  
  const text = encodeURIComponent(template)
  const url = `https://wa.me/${content.whatsapp.number}?text=${text}`
  window.open(url, '_blank')
}
</script>
