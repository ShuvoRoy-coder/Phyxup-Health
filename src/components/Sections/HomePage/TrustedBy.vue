<script setup lang="ts">
import "external-svg-loader"
import SectionSubTitle from '@/components/Ui/SectionSubTitle.vue';
import SectionTitle from '@/components/Ui/SectionTitle.vue';
import TrustedByCardImg from "@/components/Ui/TrustedByCardImg.vue";
import TrustedByCardDesicription from "@/components/Ui/TrustedByCardDesicription.vue";
import { motion } from "motion-v";

</script>

<template>
    <div class="w-full bg-sectionBg1 px-4">
        <div class="w-full max-w-[1296px] mx-auto py-8">
            <motion.div :initial="{ opacity: 0, y: 50 }"
                :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                :viewport="{ once: false, amount: 0.3 }" class="w-full space-y-5">
                <SectionTitle extra-class="text-center">
                    Trusted by <br />
                    Leading Healthcare Practices
                </SectionTitle>
                <SectionSubTitle extra-class="text-center max-w-[800px] w-full mx-auto">
                    PhyxUp Health is trusted by industry-leading practices, delivering outstanding results in patient
                    care and operational efficiency.
                </SectionSubTitle>
            </motion.div>

            <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 pt-10 gap-6">

                <div class="w-full flex flex-col gap-y-6">
                    <motion.div :initial="{ opacity: 0, y: 50 }"
                        :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                        :viewport="{ once: false, amount: 0.3 }">
                        <TrustedByCardImg image="/images/TrustedByPerson1.webp"
                            quote="PhyxUp Health greatly improved my practice. The automated billing and notes made it easy to get reimbursed for RTM, adding extra revenue for my clinic."
                            name="Andrew Martin" title="Clinic Owner" />
                    </motion.div>
                    <motion.div :initial="{ opacity: 0, y: 50 }"
                        :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                        :viewport="{ once: false, amount: 0.3 }">
                        <TrustedByCardDesicription
                            quote="PhyxUp Health transformed our practice. Patients appreciate the exercise videos, and our staff can track data more efficiently, leading to quicker decision making."
                            name="Ann Meyer" title="Physical Therapy Clinic Director" />
                    </motion.div>
                </div>


                <div class="w-full flex flex-col-reverse sm:flex-col gap-y-6">
                    <motion.div
                        :initial="{ opacity: 0, y: 50 }"
                        :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                        :viewport="{ once: false, amount: 0.3 }"
                    >
                        <TrustedByCardDesicription
                            quote="The real-time data tracking has greatly reduced the time it takes to make decisions for our clients. Our practice runs much more smoothly thanks to PhyxUp Health."
                            name="Sam Davis" title="Clinic Owner" />
                    </motion.div>

                    <motion.div
                        :initial="{ opacity: 0, y: 50 }"
                        :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                        :viewport="{ once: false, amount: 0.3 }"
                    >
                        <TrustedByCardImg image="/images/TrustedByPerson2.webp"
                            quote="The exercise videos are excellent and make it easier for patients to follow their HEPs. With easy data monitoring and reimbursement, PhyxUp Health is essential for any physical therapist."
                            name="Nicole Lawson" title="Clinic Owner" />
                    </motion.div>
                </div>


                <div class="w-full flex flex-col gap-y-6">
                    <motion.div
                        :initial="{ opacity: 0, y: 50 }"
                        :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                        :viewport="{ once: false, amount: 0.3 }"
                    >
                        <TrustedByCardImg image="/images/TrustedByPerson3.webp"
                            quote="Since we started using PhyxUp Health, our operations have been smoother and more organized. Our patients are giving great feedback, and I no longer have to worry about missing RTM billing opportunities."
                            name="Andrew Martin" title="Clinic Owner" />
                    </motion.div>

                    <motion.div
                        :initial="{ opacity: 0, y: 50 }"
                        :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                        :viewport="{ once: false, amount: 0.3 }"
                    >
                        <TrustedByCardDesicription
                            quote="Our practice is more efficient, patients are doing better, and the reimbursement feature is a great added bonus."
                            name="Mary Diaz" title="Physical Therapist" />
                    </motion.div>

                </div>


            </div>


        </div>
    </div>
</template>