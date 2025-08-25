<script setup lang="ts">
interface TrustedByCardDesicription {
  quote: string
  name: string
  title: string
  extraClass?: string
}

// define props
const props = defineProps<TrustedByCardDesicription>()
</script>

<template>
  <div
    class="bg-white px-6 sm:px-10 py-6 sm:py-7 rounded-[32px] font-mont space-y-2"
    :class="props.extraClass"
  >
    <!-- Quote Icon -->
    <svg data-src="/icons/semicolon.svg" data-cache="disabled" fill="currentColor"></svg>

    <!-- Quote -->
    <div class="text-black font-semibold text-sm sm:text-base leading-[1.4]">
      {{ props.quote }}
    </div>

    <!-- Name -->
    <div class="text-black font-semibold text-sm sm:text-base">
      {{ props.name }}
    </div>

    <!-- Title -->
    <div class="text-[#1F222C] font-medium text-xs sm:text-sm">
      {{ props.title }}
    </div>
  </div>
</template>
