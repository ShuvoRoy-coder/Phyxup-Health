<script setup lang="ts">
// interface for props
interface GradientButtonProps {
    extraClass?: string
    ternaryType?: "button" | "link"
    to?: string // for link navigation
}

// define props
const props = defineProps<GradientButtonProps>()

// define emits
const emit = defineEmits<{
    (e: "click"): void
}>()
</script>

<template>
    <!-- Button -->
    <div v-if="props.ternaryType === 'button'" class="p-[2px] group cursor-pointer relative rounded-full overflow-hidden 
           bg-[linear-gradient(45deg,rgba(255,126,0,0.35),rgba(255,120,215,0.35))] inline-block"
        :class="props.extraClass" @click="emit('click')">
        <!-- Inner button -->
        <button class="bg-white/80 relative cursor-pointer z-10 text-sm sm:text-[16px] leading-[1.25] 
             font-semibold text-center rounded-full overflow-hidden px-4 py-2.5 sm:px-6 sm:py-4">
            <span class="relative z-10">
                <slot />
            </span>
            <div class="bg-[linear-gradient(45deg,rgba(255,126,0),rgba(255,120,215))] absolute inset-0
               transition-all duration-300 opacity-[15%] group-hover:opacity-0"></div>
            <div class="bg-[linear-gradient(45deg,rgba(255,120,215),rgba(255,126,0))] absolute inset-0
               transition-all duration-300 opacity-0 group-hover:opacity-[35%]"></div>
        </button>
    </div>

    <!-- Router Link -->
    <RouterLink v-else-if="props.ternaryType === 'link'" :to="props.to || '/'" class="p-[2px] group cursor-pointer relative rounded-full overflow-hidden 
           bg-[linear-gradient(45deg,rgba(255,126,0,0.35),rgba(255,120,215,0.35))] inline-block"
        :class="props.extraClass">
        <div class="bg-white/80 relative cursor-pointer z-10 text-sm sm:text-[16px] leading-[1.25] 
             font-semibold text-center rounded-full overflow-hidden px-4 py-2.5 sm:px-6 sm:py-4">
            <span class="relative z-10">
                <slot />
            </span>
            <div class="bg-[linear-gradient(45deg,rgba(255,126,0),rgba(255,120,215))] absolute inset-0
               transition-all duration-300 opacity-[15%] group-hover:opacity-0"></div>
            <div class="bg-[linear-gradient(45deg,rgba(255,120,215),rgba(255,126,0))] absolute inset-0
               transition-all duration-300 opacity-0 group-hover:opacity-[35%]"></div>
        </div>
    </RouterLink>
</template>
