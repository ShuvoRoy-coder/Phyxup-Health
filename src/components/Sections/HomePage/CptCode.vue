<script setup lang="ts">
import CptCard from '@/components/Ui/CptCard.vue';
import SectionSubTitle from '@/components/Ui/SectionSubTitle.vue';
import SectionTitle from '@/components/Ui/SectionTitle.vue';
import TernaryButton from '@/components/Ui/TernaryButton.vue';
import { motion } from 'motion-v';

</script>

<template>
    <div class="w-full max-w-[1648px] mx-auto px-4 pb-10">

        <motion.div 
            :initial="{ opacity: 0, y: 50 }"
            :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
            :viewport="{ once: false, amount: 0.3 }"
            class="flex flex-col items-center justify-center gap-3 sm:gap-8 2xl:gap-14">
            <!-- Gradient border wrapper -->
            <TernaryButton ternaryType="link" to="/">
                 CPT Codes
            </TernaryButton>

            <SectionTitle extra-class="text-center">
                What Is Remote Therapeutic Monitoring (RTM)?
            </SectionTitle>

            <SectionSubTitle extra-class="text-center">
                The 2022 Medicare Fee Schedule introduced new CPT codes for remotely monitoring patients with
                musculoskeletal conditions.<br />

                Designed for patients with musculoskeletal conditions, RTM extends care
                beyond the clinic.<br />

                It improves engagement, supports adherence, and guides patients between in-person visits.
            </SectionSubTitle>
        </motion.div>

        <!-- card area start -->
        <motion.div 
            :initial="{ opacity: 0, y: 50 }"
            :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
            :viewport="{ once: false, amount: 0.3 }"
            class="w-full max-w-[1224px] mx-auto py-5 md:py-9">
            <div class="w-full grid grid-cols-1 md:grid-cols-2 gap-6">

                <motion.div
                    :initial="{ opacity: 0, y: 50 }"
                    :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                    :viewport="{ once: false, amount: 0.3 }"
                >
                    <CptCard :code="98975" :price="19" text_1="Reimbursement for initial setup patient education"
                        text_2="Billing Frequency: Once per Episode"
                        extra-class="bg-[linear-gradient(145deg,rgba(89,147,234,0),rgba(255,126,0,0.2))]" />
                </motion.div>

                <motion.div
                    :initial="{ opacity: 0, y: 50 }"
                    :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                    :viewport="{ once: false, amount: 0.3 }"
                >
                    <CptCard :code="98977" :price="55" text_1="Reimbursement for device & data transmission"
                        text_2="Billing Frequency: Once per 30 days"
                        extra-class="bg-[linear-gradient(145deg,rgba(89,147,234,0),rgba(0,178,255,0.2))]" />
                </motion.div>

                <motion.div
                    :initial="{ opacity: 0, y: 50 }"
                    :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                    :viewport="{ once: false, amount: 0.3 }"
                >
                    <CptCard :code="98980" :price="50" text_1="Reimbursement for the first 20 minutes of RTM treatment service in a month"
                    text_2="Billing Frequency: Once per Calendar Month"
                    extra-class="bg-[linear-gradient(145deg,rgba(89,147,234,0),rgba(79,206,0,0.2))]" />
                </motion.div>

                <motion.div
                    :initial="{ opacity: 0, y: 50 }"
                    :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                    :viewport="{ once: false, amount: 0.3 }"
                >
                    <CptCard :code="98981" :price="40" text_1="Reimbursement for each additional 20 minutes of RTM treatment service in a month"
                    text_2="Billing Frequency: Multiple times per Calendar Month"
                    extra-class="bg-[linear-gradient(145deg,rgba(89,147,234,0),rgba(255,0,229,0.2))]" />
                </motion.div>

            </div>
        </motion.div>

        <motion.p 
            :initial="{ opacity: 0, y: 50 }"
            :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
            :viewport="{ once: false, amount: 0.3 }"
            class="text-center font-medium text-sm md:text-base">
            *Reimbursement amount is based on average Medicare rates and may be different from patient’s health
            insurance rates.
        </motion.p>
    </div>
</template>