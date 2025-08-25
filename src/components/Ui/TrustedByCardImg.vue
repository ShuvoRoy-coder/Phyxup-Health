<script setup lang="ts">
interface TrustedByCardImg {
    image: string
    quote: string
    name: string
    title: string
    extraClass?: string
}

// define props
const props = defineProps<TrustedByCardImg>()
</script>

<template>
    <div class="relative w-full rounded-[32px] overflow-hidden" :class="props.extraClass">
        <!-- Background Image -->
        <img :src="props.image" alt="testimonial image" class="w-full object-cover" />

        <!-- Overlay -->
        <div class="bg-[linear-gradient(180deg,rgba(31,34,45,0)_0%,rgba(66,68,72,0.58)_20%,rgba(39,46,70,0.88)_100%)]
             absolute z-10 bottom-0 left-0 w-full text-white px-6 sm:px-10 py-6 sm:py-7 font-mont space-y-2">
            <!-- Quote Icon -->
            <svg data-src="/icons/semicolonWhite.svg" fill="currentColor"></svg>

            <!-- Quote -->
            <div class="font-semibold text-sm sm:text-base leading-[1.4]">
                {{ props.quote }}
            </div>

            <!-- Name -->
            <div class="font-semibold text-sm sm:text-base">
                {{ props.name }}
            </div>

            <!-- Title -->
            <div class="font-medium text-xs sm:text-sm opacity-90">
                {{ props.title }}
            </div>
        </div>
    </div>
</template>
