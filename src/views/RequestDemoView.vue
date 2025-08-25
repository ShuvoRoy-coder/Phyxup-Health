<script setup lang="ts">
import "external-svg-loader";
import SectionTitle from '@/components/Ui/SectionTitle.vue';
import { motion } from "motion-v";

</script>

<template>
    <div class="bg-sectionBg1 pt-12 xl:pt-16 2xl:pt-[90px]">
        <motion.div 
            :initial="{ opacity: 0, y: 50 }"
            :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
            :viewport="{ once: false, amount: 0.3 }"
            class="py-[100px]">
            <SectionTitle extra-class="text-center px-4">
                Schedule a time to meet with Sangwon
            </SectionTitle>

            <motion.div 
                :initial="{ opacity: 0, y: 50 }"
                :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                :viewport="{ once: false, amount: 0.3 }"
                class="w-full relative">
                <!-- bg-image -->

                <div class="w-full absolute top-[200px] min-[1490px]:bottom-0">
                    <img src="/images/requestDemoPageBg.webp" alt="bg-img" class="w-full">
                </div>

                <div class="max-w-[1664px] w-full mx-auto pt-20 px-4 relative z-10">
                    <div class="flex flex-col-reverse min-[1490px]:flex-row items-center justify-center gap-8">
                        <!-- calender image -->
                         <motion.div 
                            :initial="{ opacity: 0, y: 50 }"
                            :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                            :viewport="{ once: false, amount: 0.3 }"
                            class="max-w-[550px] 2xl:max-w-[672px] w-full">
                            <img src="/images/Calendar.webp" alt="calendar" class="rounded-2xl drop-shadow-xl">
                         </motion.div>
    
                         <div class="flex flex-col md:flex-row gap-12 items-center md:items-start">
                             <!-- profile area start -->
                             <motion.div 
                                :initial="{ opacity: 0, y: 50 }"
                                :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                                :viewport="{ once: false, amount: 0.3 }"
                                class="bg-white border-l-[2px] rounded-r-2xl overflow-hidden border-[#0083FF] drop-shadow-xl px-8 py-10 space-y-4 max-w-[300px] 2xl:max-w-[358px] w-full">
                                <div class="w-full aspect-square">
                                    <img src="/images/sangwon_lim.webp" alt="person" class="w-full h-full object-cover">
                                </div>
        
                                <div class="text-primaryText flex flex-col items-center">
                                    <div class="font-inter text-[18px] sm:text-[24px] md:text-[28px] 2xl:text-[36px] leading-[1.5] flex items-center gap-4">
                                        <div class="font-semibold">
                                            Sangwon Lim
                                        </div>
        
                                        <svg class="text-[18px] sm:text-[24px] md:text-[28px] 2xl:size-[36px]" data-src="/icons/linkedIn.svg" fill="currentColor"></svg>
        
                                    </div>
        
                                    <div class="font-mont text-center text-sm md:text-base 2xl:text-lg py-4">
                                        PhyxUp Health Founder & CEO
                                    </div>
        
        
        
                                </div>
                             </motion.div>
    
                             <!-- description area -->
                             <motion.div 
                                :initial="{ opacity: 0, y: 50 }"
                                :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                                :viewport="{ once: false, amount: 0.3 }"
                                class="bg-white border-r-[2px] rounded-l-2xl overflow-hidden border-primary drop-shadow-xl p-8 max-w-[500px] 2xl:max-w-[558px] w-full
                                text-[16px] sm:text-[18px] md:text-[20px] 2xl:text-[24px] leading-[1.32]"
                            >
    
                                Sangwon, a former physical therapist and healthcare analyst, founded PhyxUp Health to help providers track patient progress, improve health outcomes, and receive reimbursement through Remote Therapeutic Monitoring (RTM).<br/><br/>
    
                                PhyxUp Health was incubated at the Harvard Innovation Lab in 2019. Since then, Sangwon has grown the company into a trusted source of rehabilitation care. PhyxUp remains focused on making RTM smarter, more efficient, and patient focused.
    
                             </motion.div>
    
                         </div>
    
    
                    </div>
                </div>
            </motion.div>

        </motion.div>
    </div>
</template>