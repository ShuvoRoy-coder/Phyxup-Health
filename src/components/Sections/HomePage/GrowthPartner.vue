<script setup lang="ts">
import SectionSubTitle from '@/components/Ui/SectionSubTitle.vue';
import SectionTitle from '@/components/Ui/SectionTitle.vue';
import SubSectionSubTitle from '@/components/Ui/SubSectionSubTitle.vue';
import SubSectionTitle from '@/components/Ui/SubSectionTitle.vue';
import { motion } from 'motion-v';

</script>

<template>
    <div class="w-full relative">
        
        <!-- background color -->
        <div class="w-full absolute h-full top-0 left-0 flex flex-col justify-between">

            <svg class="max-w-[1920px] w-full mx-auto shrink-0" viewBox="0 0 1921 271" fill="none"
                xmlns="http://www.w3.org/2000/svg">
                <path
                    d="M1920.5 270.518H0C0 170.52 215.784 100.016 255.5 90.0182C1048 -109.48 1639 76.5182 1782 134.518C1896.4 180.918 1922 244.518 1920.5 270.518Z"
                    fill="#F5FAFF" />
            </svg>

            <div class="w-full h-full bg-[#F5FAFF]"></div>

            <svg class="max-w-[1920px] w-full mx-auto shrink-0 rotate-180" viewBox="0 0 1921 271" fill="none"
                xmlns="http://www.w3.org/2000/svg">
                <path
                    d="M1920.5 270.518H0C0 170.52 215.784 100.016 255.5 90.0182C1048 -109.48 1639 76.5182 1782 134.518C1896.4 180.918 1922 244.518 1920.5 270.518Z"
                    fill="#F5FAFF" />
            </svg>

        </div>

        <div class="w-full px-4 pt-[50px] min-[500px]:pt-[80px] sm:pt-[100px] lg:pt-[120px] pb-[20px] sm:pb-[30px] relative z-10">
            
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
                    <div class="space-y-2">
                        <SubSectionTitle>
                            More Revenue, Zero Extra Work
                        </SubSectionTitle>
                        <div class="max-w-[690px] w-full">    
                            <SubSectionSubTitle>
                                Generate $10K+ in monthly RTM revenue through a fully managed, AI-powered process without adding staff or hours.
                            </SubSectionSubTitle>
                        </div>
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

                    <div class="space-y-2">
                        <SubSectionTitle>
                            Patients Who Stay & Succeed
                        </SubSectionTitle>
                        <div class="max-w-[690px] w-full">    
                            <SubSectionSubTitle>
                                Improve engagement, satisfaction, and outcomes by keeping patients connected and on track between visits.
                            </SubSectionSubTitle>
                        </div>
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

                    <div class="space-y-2">
                        <SubSectionTitle>
                            Stay Competitive
                        </SubSectionTitle>
                        <div class="max-w-[690px] w-full">    
                            <SubSectionSubTitle>
                                Offer smarter, modern care that strengthens your brand and positions your clinic ahead of competitors.
                            </SubSectionSubTitle>
                        </div>
                    </div>
                </div>

                <div class="max-w-[1200px] mx-auto">
                    <img src="/images/GrowthParthnerBanner3.webp" alt="banner">
                </div>
            </motion.div>

        </div>

        

    </div>
</template>