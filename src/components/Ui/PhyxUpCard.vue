<script setup lang="ts">
// interface for props
interface phyxUpCard {
  img_src: string
  title: string
  subtitle: string
}

// define props
const props = defineProps<phyxUpCard>()

</script>


<template>
    <div class="w-full space-y-6 md:space-y-10">
        <div class="w-full drop-shadow-lg">
            <img :src="img_src" alt="">
        </div>
        <div class="space-y-2 md:space-y-4">
            <div
                class="text-primaryText mx-auto max-w-[315px] w-full font-semibold text-center text-[18px] sm:text-[24px] lg:text-[32px] leading-[1.5]">
                {{ title }}
            </div>
            <div class="text-black text-center font-medium text-[14px] sm:text-[18px] lg:lg:text-[20px] leading-[1.5] ">
                {{ subtitle }}
            </div>
        </div>
    </div>
</template>