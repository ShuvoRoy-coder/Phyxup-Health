<script setup lang="ts">
// interface for props
interface cptCard {
    extraClass?: string
    code: Number
    price: Number
    text_1: string
    text_2: string
}

// define props
const props = defineProps<cptCard>()

</script>


<template>
    <div class="px-[30px] py-[50px] sm:px-[41px] sm:py-[68px]"
        :class="props.extraClass"
                
    >
        <div class="text-black font-black text-[24px] lg:text-[28px] 2xl:text-[32px] leading-[1.25] font-mont sm:pl-[20px] 2xl:pl-[33px]">
            CPT Code <span class="text-primary">{{ code }}</span>
        </div>

        <div class="text-center py-11 2xl:py-15">
            <div class="bg-[linear-gradient(-80deg,#696969,#001352)] inline-block 
                            text-transparent bg-clip-text
                            text-[60px] lg:text-[65px] 2xl:text-[86px] 
                            leading-[1.25] font-medium font-inter tracking-[-1px]">
                ${{price}}*
            </div>
        </div>

        <div class="font-mont text-primaryText 
            text-[18px] lg:text-[20px] 2xl:text-[24px]
            leading-[1.25] font-medium tracking-[-1px] 
            space-y-3  2xl:space-y-4">

            <div>
                {{ text_1 }}
            </div>
            <div>
                {{ text_2 }}
            </div>
        </div>

    </div>
</template>