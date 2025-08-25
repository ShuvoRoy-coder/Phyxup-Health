<script setup lang="ts">
import PrimaryButton from '@/components/Ui/PrimaryButton.vue';
import SecondaryButton from '@/components/Ui/SecondaryButton.vue';
import { motion } from 'motion-v';

</script>

<template>
    <div class="relative pt-12 xl:pt-16 2xl:pt-[90px]">

        <!-- background image -->
        <div class="w-full h-[550px] sm:h-[700px] lg:h-[1245px] absolute top-0 left-0">
            <img src="/images/hero-bg.webp" alt="img" class="w-full h-full object-cover">
        </div>

        <motion.div 
            :initial="{ opacity: 0, y: 50 }"
            :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
            :viewport="{ once: false, amount: 0.3 }"
            class="relative z-10 max-w-[1410px] w-full px-4 mx-auto 
            py-[50px] sm:py-[80px] lg:py-[103px]"
        >
            
            <div class="text-base bg-gradient-to-r from-[#E50004] to-[#100C8E]
                text-transparent bg-clip-text
                leading-[18px] sm:text-[22px] lg:text-[26px] 
                sm:leading-[1.25] font-medium text-center">
                First Remote Therapeutic Monitoring (RTM) with AI Agent
            </div>
            <h1
                class="text-primaryText font-medium font-inter 
                    tracking-[-1.5px] text-center 
                    text-[30px] leading-[30px] 
                    sm:text-[40px] sm:leading-[40px] 
                    lg:text-[80px] lg:leading-[80px] 
                    py-[30px] sm:py-[45px] lg:py-[72px]"
                >
                AI-Powered RTM <br />
                That Grows Revenue 30%
            </h1>
            <p class="text-primaryText font-medium text-center 
                text-[16px] leading-[20px] 
                sm:text-[20px] sm:leading-[24px] 
                lg:text-[24px] lg:leading-[30px] 
                max-w-[700px] w-full mx-auto"
            >
                Grow your practice with fully managed RTM solution
                from patient check-in to billing
            </p>

            <!-- button area start -->
            <div class="flex items-center justify-center gap-2 sm:gap-9 pt-10 sm:pt-14 lg:pt-20">
                <PrimaryButton primaryType="link" to="/request-demo" text="Request Demo" extraClass="min-w-[45%] sm:min-w-[172px] !text-[14px] !leading-[18px] sm:!text-[16px] sm:!leading-[22px]"/>
                <SecondaryButton secondaryType="button" text="Free Trial" extraClass="min-w-[45%] sm:min-w-[172px] !text-[14px] !leading-[18px] sm:!text-[16px] sm:!leading-[22px]"/>
            </div>
        </motion.div>
        
        <!-- image start -->
         <motion.div
            :initial="{ opacity: 0, y: 50 }"
            :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
            :viewport="{ once: false, amount: 0.3 }"
            class="relative z-10 max-w-[1750px] w-full mx-auto px-4 sm:px-12">
            <img src="/images/hero-dashboard.webp" alt="img">
         </motion.div>

    </div>
</template>