<template>
  <button
    :class="[
      'inline-flex items-center justify-center font-medium rounded-full transition-all duration-300',
      sizeClasses[size],
      variantClasses[variant]
    ]"
    v-bind="$attrs"
  >
    <slot></slot>
  </button>
</template>

<script setup>
const props = defineProps({
  variant: {
    type: String,
    default: 'primary',
    validator: (v) => ['primary', 'outline', 'white'].includes(v)
  },
  size: {
    type: String,
    default: 'md',
    validator: (v) => ['sm', 'md', 'lg'].includes(v)
  }
})

const sizeClasses = {
  sm: 'px-4 py-2 text-sm',
  md: 'px-6 py-3 text-base',
  lg: 'px-8 py-4 text-lg'
}

const variantClasses = {
  primary: 'bg-[#22E27A] text-[#0B1220] hover:bg-white glow-effect',
  outline: 'border-2 border-[#22E27A] text-[#22E27A] hover:bg-[#22E27A] hover:text-[#0B1220]',
  white: 'bg-white text-[#0B1220] hover:bg-gray-200'
}
</script>
