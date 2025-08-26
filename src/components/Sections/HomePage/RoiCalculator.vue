<script setup lang="ts">
import { ref, computed } from "vue";
import RangeInput from "@/components/Ui/RangeInput.vue";
import SectionSubTitle from "@/components/Ui/SectionSubTitle.vue";
import SectionTitle from "@/components/Ui/SectionTitle.vue";
import "external-svg-loader";
import PrimaryButton from "@/components/Ui/PrimaryButton.vue";
import { motion } from "motion-v";

// state
const patients = ref(40);

const cptCodes = ref([
    { price: 19, code: 98975, units: 1, max: 1 },
    { price: 55, code: 98977, units: 1, max: 1 },
    { price: 50, code: 98980, units: 1, max: 1 },
    { price: 40, code: 98981, units: 1, max: 3 }
]);

// compute reimbursement
const total = computed(() => {
    let sum = 0;
    cptCodes.value.forEach(cpt => {
        sum += patients.value * cpt.price * cpt.units;
    });
    return sum;
});
</script>

<template>
    <div class="bg-sectionBg1 px-4 pt-12 pb-20">
        <motion.div 
            :initial="{ opacity: 0, y: 50 }"
            :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
            :viewport="{ once: false, amount: 0.3 }"
            class="bg-white relative rounded-2xl overflow-hidden max-w-[1280px] w-full mx-auto px-4 md:px-8 pt-8 pb-16">
            <div class="relative z-10">

                <div class="space-y-4">
                    <SectionTitle extra-class="text-center">ROI Calculator</SectionTitle>
                    <SectionSubTitle extra-class="text-center">Estimate your potential savings through PhyxUp Health’s
                        automated RTM reimbursement</SectionSubTitle>
                </div>

                <div class="pt-10 grid grid-cols-1 md:grid-cols-2 gap-10 md:gap-2">
                    <!-- Left Side -->
                    <div class="w-full">
                        <!-- Patients -->
                        <div>
                            <div class="flex items-center gap-2">
                                <svg class="size-4 fill-black" data-src="/icons/person.svg" fill="currentColor"></svg>
                                <div class="text-black">Number of Patients</div>
                            </div>
                            <RangeInput v-model="patients" :min="0" :max="100" />
                        </div>

                        <!-- CPT Codes -->
                        <div class="flex items-center gap-2 pt-[28px] pb-[18px]">
                            <svg class="w-[15px] fill-black" data-src="/icons/book.svg" data-cache="disabled"
                                fill="currentColor"></svg>
                            <h3 class="">Units by CPT Code</h3>
                        </div>

                        <div class="w-full space-y-6">
                            <div v-for="(cpt, index) in cptCodes" :key="cpt.code">
                                <RangeInput v-model="cpt.units" :code="cpt.code.toString()" :price="'$' + cpt.price"
                                    :min="0" :max="cpt.max" />
                            </div>
                        </div>

                    </div>

                    <!-- Right Side -->
                    <div class="w-full max-w-[532px] mx-auto md:mx-0 md:ml-auto h-full md:pl-[30px] md:py-[5px]">
                        <div class="bg-white h-full rounded-2xl flex flex-col items-center justify-center py-8 px-4">
                            <p class="px-4 font-medium text-xl leading-[1.25] sm:text-2xl text-center">Your Estimated Reimbursement:</p>

                            <h2 class="px-4 my-8 w-full text-center font-semibold text-[36px] sm:text-[54px] leading-[1.25] h-[70px] sm:h-[93px]
                                flex items-center justify-center
                                bg-[url('/images/rotTextBg.webp')] bg-no-repeat bg-cover bg-center">
                                ${{ total.toLocaleString() }}
                            </h2>

                            <div class="w-full px-4 text-center flex items-center justify-center">
                                <PrimaryButton primary-type="button" text="Email The Result" extra-class="min-w-[195px]">
                                    <svg width="8" height="12" viewBox="0 0 8 12" fill="none"
                                        xmlns="http://www.w3.org/2000/svg">
                                        <path d="M2 2L6 6L2 10" stroke="white" stroke-width="3" stroke-linecap="round"
                                            stroke-linejoin="round" />
                                    </svg>
                                </PrimaryButton>

                            </div>
                        </div>
                    </div>

                </div>
            </div>

            <div
                class="absolute left-0 right-auto md:left-auto md:right-0 md:translate-x-[12%] bottom-0 md:bottom-auto top-auto md:top-1/2 md:-translate-y-[30%] w-full md:w-[60%] h-[350px] min-[550px]:h-[400px] md:h-auto">
                <img src="/images/rotCalculatorRightBg.webp" alt="img" class="w-full">
            </div>

        </motion.div>
    </div>
</template>
