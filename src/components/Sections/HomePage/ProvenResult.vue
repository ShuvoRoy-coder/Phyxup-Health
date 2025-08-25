<script setup lang="ts">
import ProvenResultCard from '@/components/Ui/ProvenResultCard.vue';
import SectionSubTitle from '@/components/Ui/SectionSubTitle.vue';
import SectionTitle from '@/components/Ui/SectionTitle.vue';
import TernaryButton from '@/components/Ui/TernaryButton.vue';
import { motion } from 'motion-v';

</script>

<template>
    <div class="w-full relative">
        
        <div class="w-full max-w-[1663px] mx-auto relative">
            <div class="w-full absolute top-0 h-full left-1/2 -translate-x-1/2">
                <img src="/images/trangle-bg.webp" alt="bg" class="w-full h-full object-cover">
            </div>
    
            <div class="pt-10 px-4 pb-5 flex items-center justify-center">
                <TernaryButton ternary-type="link" to="/" extra-class="min-w-[152px]">
                    Benefits
                </TernaryButton>
            </div>
        </div>

        <div class="w-full mx-auto bg-sectionBg1 px-4">

            <motion.div 
                :initial="{ opacity: 0, y: 50 }"
                :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                :viewport="{ once: false, amount: 0.3 }"
                class="w-full max-w-[1226px] mx-auto py-2">
                <div class="w-full space-y-5">
                    <SectionTitle extra-class="text-center">
                        Proven Results with AI + Clinical Expertise
                    </SectionTitle>
                    <SectionSubTitle extra-class="text-center max-w-[800px] w-full mx-auto">
                        PhyxUp Health combines advanced AI with licensed PT-led care to deliver the highest RTM ROI, maximizing both revenue and patient outcomes.
                    </SectionSubTitle>
                </div>
            </motion.div>

            <motion.div 
                :initial="{ opacity: 0, y: 50 }"
                :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                :viewport="{ once: false, amount: 0.3 }"
                class="max-w-[1226px] mx-auto space-y-4 md:space-y-8 py-10 sm:py-[60px] lg:py-[100px]">
                
                <motion.div 
                    :initial="{ opacity: 0, y: 50 }"
                    :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                    :viewport="{ once: false, amount: 0.3 }"
                    class="grid grid-cols-1 sm:grid-cols-2 gap-4 md:gap-8 sm:pl-6 lg:pl-10">
                    
                    <motion.div
                        :initial="{ opacity: 0, y: 50 }"
                        :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                        :viewport="{ once: false, amount: 0.3 }"
                    >
                        <ProvenResultCard
                            highlight-text="$10K +"
                            title="Monthly per PT"
                            description="Average RTM reimbursement achieved with AI-powered tracking."
                            bg-color="#B7FFCB"
                            border-color="#B7FFCB"
                        />
                    </motion.div>

                    <motion.div
                        :initial="{ opacity: 0, y: 50 }"
                        :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                        :viewport="{ once: false, amount: 0.3 }"
                    >
                        <ProvenResultCard
                            highlight-text="$165"
                            title="Per Patient"
                            description="Minimum monthly reimbursement, with billing ensured by our dedicated team."
                            bg-color="#FFE3CF"
                            border-color="#FFE3CF"
                        />
                    </motion.div>
    
                </motion.div>

                <motion.div 
                    :initial="{ opacity: 0, y: 50 }"
                    :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                    :viewport="{ once: false, amount: 0.3 }"
                    class="grid grid-cols-1 sm:grid-cols-2 gap-4 md:gap-8 sm:pr-6 lg:pr-10">

                    <motion.div
                        :initial="{ opacity: 0, y: 50 }"
                        :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                        :viewport="{ once: false, amount: 0.3 }"
                    >
                        <ProvenResultCard
                            highlight-text="94%"
                            title="Patient Satisfaction"
                            description="94% of RTM patients report receiving higher-quality care through RTM."
                            bg-color="#B1F6FF"
                            border-color="#B1F6FF"
                        />
                    </motion.div>

                    <motion.div
                        :initial="{ opacity: 0, y: 50 }"
                        :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                        :viewport="{ once: false, amount: 0.3 }"
                    >
                        <ProvenResultCard
                            highlight-text="80%"
                            title="Patient Engagement"
                            description="4 out of 5 patients actively engage with RTM, ensuring better outcomes."
                            bg-color="#D2CCFF"
                            border-color="#D2CCFF"
                        />
                    </motion.div>
    
                </motion.div>
            </motion.div>

        </div>


    </div>
</template>