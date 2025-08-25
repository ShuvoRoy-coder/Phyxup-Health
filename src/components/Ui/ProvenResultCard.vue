<script setup lang="ts">
// Props interface
interface ProverResultCardProps {
    highlightText: string
    title: string
    description: string
    bgColor?: string
    borderColor?: string
    extraClass?: string
}

const props = defineProps<ProverResultCardProps>()
</script>

<template>
    <div class="w-full text-primaryText leading-[1.25] bg-white drop-shadow-xl py-7 px-6 space-y-4 md:space-y-8 border-l-[4px] rounded-r-xl"
        :style="{ borderColor: props.borderColor || '#B7FFCB' }" :class="props.extraClass">
        <!-- Highlight Box -->
        <div class="inline-block rounded-full font-semibold text-[25px] sm:text-[30px] lg:text-[40px] p-4"
            :style="{ backgroundColor: props.bgColor || '#B7FFCB' }">
            {{ props.highlightText }}
        </div>

        <!-- Title -->
        <div class="font-medium text-[20px] sm:text-[25px] lg:text-[30px]">
            {{ props.title }}
        </div>

        <!-- Description -->
        <div class="font-medium text-[15px] sm:text-[20px] lg:text-[24px] leading-[1.25]">
            {{ props.description }}
        </div>
    </div>
</template>
