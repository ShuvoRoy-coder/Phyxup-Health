<script setup lang="ts">
import PhyxUpCard from '@/components/Ui/PhyxUpCard.vue';
import PrimaryButton from '@/components/Ui/PrimaryButton.vue';
import SectionSubTitle from '@/components/Ui/SectionSubTitle.vue';
import SectionTitle from '@/components/Ui/SectionTitle.vue';
import { motion } from 'motion-v';

</script>

<template>
    <div class="w-full px-4 bg-white pb-[20px]">
        <motion.div 
            :initial="{ opacity: 0, y: 50 }"
            :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
            :viewport="{ once: false, amount: 0.3 }"
            class="max-w-[636px] w-full mx-auto flex flex-col items-center gap-4 pt-8 md:pt-16 pb-10 md:pb-20">
            <SectionTitle extra-class="text-center">
                Why PhyxUp Health
            </SectionTitle>
            <SectionSubTitle extra-class="text-center">
                AI-Powered Remote Therapeutic Monitoring Designed for Rehab Professionals
            </SectionSubTitle>
            <PrimaryButton primary-type="link" to="/request-demo" text="Request Demo" extra-class="min-w-full sm:min-w-[360px] mx-auto"/>
        </motion.div>

        <!-- images area -->
         <motion.div 
            :initial="{ opacity: 0, y: 50 }"
            :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
            :viewport="{ once: false, amount: 0.3 }"
            class="max-w-[1305px] w-full mx-auto grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-8">
            
            <!-- img 1 -->
             <motion.div
                :initial="{ opacity: 0, y: 50 }"
                :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                :viewport="{ once: false, amount: 0.3 }"
             >
                 <PhyxUpCard img_src="/images/PhyxUpHealthBanner1.webp" 
                     title="PT-Led Care, Every Step" 
                     subtitle="Licensed physical therapists handle all patient check-ins and create and update every care program, ensuring clinical quality and personalized support."
                 />
             </motion.div>
            <!-- img 2 -->
             <motion.div :initial="{ opacity: 0, y: 50 }"
                :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                :viewport="{ once: false, amount: 0.3 }">
                <PhyxUpCard img_src="/images/PhyxUpHealthBanner2.webp" 
                    title="High Engagement, Better Outcomes" 
                    subtitle="Our patient app keeps engagement rates above 80% and delivers over 50% better outcomes compared to non-monitored programs."
                />
             </motion.div>
            <!-- img 3 -->

            <motion.div :initial="{ opacity: 0, y: 50 }"
                :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                :viewport="{ once: false, amount: 0.3 }"
            >
                <PhyxUpCard img_src="/images/PhyxUpHealthBanner3.webp" 
                    title="AI + Expert Team = Maximum ROI" 
                    subtitle="With PT expertise, AI efficiency, and proven billing processes, we deliver the most cost-effective RTM and reliable reimbursement results."
                />
            </motion.div>

         </motion.div>
    </div>
</template>