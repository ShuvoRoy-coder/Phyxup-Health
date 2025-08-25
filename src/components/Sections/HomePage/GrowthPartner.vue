<script setup lang="ts">
import SectionSubTitle from '@/components/Ui/SectionSubTitle.vue';
import SectionTitle from '@/components/Ui/SectionTitle.vue';
import SubSectionSubTitle from '@/components/Ui/SubSectionSubTitle.vue';
import SubSectionTitle from '@/components/Ui/SubSectionTitle.vue';
import { motion } from 'motion-v';

</script>

<template>
    <div class="w-full">
        <svg class="max-w-[1920px] w-full mx-auto translate-y-1" viewBox="0 0 1921 271" fill="none"
            xmlns="http://www.w3.org/2000/svg">
            <path
                d="M1920.5 270.518H0C0 170.52 215.784 100.016 255.5 90.0182C1048 -109.48 1639 76.5182 1782 134.518C1896.4 180.918 1922 244.518 1920.5 270.518Z"
                fill="#F5FAFF" />
        </svg>

        <div 
            class="w-full bg-[#F5FAFF] px-4">
            
            <motion.div 
                :initial="{ opacity: 0, y: 50 }"
                :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                :viewport="{ once: false, amount: 0.3 }"
                class="pb-10 max-w-[1150px] mx-auto w-full">
                <SectionTitle>
                    A Growth Partner That Delivers Real Impact
                </SectionTitle>
            </motion.div>

            <!-- banner 1 start -->
            <motion.div 
                :initial="{ opacity: 0, y: 50 }"
                :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                :viewport="{ once: false, amount: 0.3 }"
                class="w-full">
                <div class="max-w-[1150px] mx-auto w-full pb-5">
                    <div class="max-w-[690px] w-full space-y-1">
                        <SubSectionTitle>
                            More Revenue, Zero Extra Work
                        </SubSectionTitle>
                        
                        <SubSectionSubTitle>
                            Generate $10K+ in monthly RTM revenue through a fully managed, AI-powered process without adding staff or hours.
                        </SubSectionSubTitle>
                    </div>
                </div>

                <div class="max-w-[1200px] mx-auto">
                    <img src="/images/GrowthParthnerBanner1.webp" alt="banner">
                </div>
            </motion.div>


            <!-- banner 2 start -->
            <motion.div 
                :initial="{ opacity: 0, y: 50 }"
                :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                :viewport="{ once: false, amount: 0.3 }"
                class="w-full pt-10 md:pt-20">    
                <div class="max-w-[1150px] mx-auto w-full pb-10">
                    <div class="max-w-[690px] w-full space-y-1">
                        <SubSectionTitle>
                           Patients Who Stay & Succeed
                        </SubSectionTitle>
                        
                        <SubSectionSubTitle>
                            Improve engagement, satisfaction, and outcomes by keeping patients connected and on track between visits.
                        </SubSectionSubTitle>
                    </div>
                </div>

                <div class="max-w-[1200px] mx-auto">
                    <img src="/images/GrowthParthnerBanner2.webp" alt="banner">
                </div>
            </motion.div>


            <!-- banner 3 start -->
            <motion.div 
                :initial="{ opacity: 0, y: 50 }"
                :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                :viewport="{ once: false, amount: 0.3 }"
                class="w-full pt-10 md:pt-20">    
                <div class="max-w-[1150px] mx-auto w-full pb-10">
                    <div class="max-w-[690px] w-full space-y-1">
                        <SubSectionTitle>
                           Stay Competitive
                        </SubSectionTitle>
                        
                        <SubSectionSubTitle>
                            Offer smarter, modern care that strengthens your brand and positions your clinic ahead of competitors.
                        </SubSectionSubTitle>
                    </div>
                </div>

                <div class="max-w-[1200px] mx-auto">
                    <img src="/images/GrowthParthnerBanner3.webp" alt="banner">
                </div>
            </motion.div>

        </div>

        <svg class="max-w-[1920px] w-full mx-auto rotate-180 -translate-y-2" viewBox="0 0 1921 271" fill="none"
            xmlns="http://www.w3.org/2000/svg">
            <path
                d="M1920.5 270.518H0C0 170.52 215.784 100.016 255.5 90.0182C1048 -109.48 1639 76.5182 1782 134.518C1896.4 180.918 1922 244.518 1920.5 270.518Z"
                fill="#F5FAFF" />
        </svg>

    </div>
</template>