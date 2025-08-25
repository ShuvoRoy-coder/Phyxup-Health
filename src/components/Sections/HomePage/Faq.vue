<script setup lang="ts">
import SectionTitle from "@/components/Ui/SectionTitle.vue";
import { motion } from "motion-v";
import { ref } from "vue";

// interface for each FAQ
interface FaqItem {
    question: string;
    answer: string;
}

// props
const props = defineProps<{
    faqs: FaqItem[];
}>();

// track the currently open index
const openIndex = ref<number | null>(null);

// toggle function
const toggleFaq = (index: number) => {
    openIndex.value = openIndex.value === index ? null : index;
};
</script>

<template>
    <section class="w-full bg-sectionBg1 px-4 py-10 md:py-20">
        <div class="max-w-[1424px] w-full mx-auto space-y-10 md:space-y-16">
            <motion.div 
                :initial="{ opacity: 0, y: 50 }"
                :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                :viewport="{ once: false, amount: 0.3 }"
                class="space-y-1">
                <div class="max-w-[200px] w-full mx-auto">
                    <img src="/logos/phyxcp-health.webp" alt="logo" class="w-full object-cover">
                </div>
                <SectionTitle extra-class="text-center">
                    Frequently Asked Questions
                </SectionTitle>
            </motion.div>

            <motion.div 
                :initial="{ opacity: 0, y: 50 }"
                :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                :viewport="{ once: false, amount: 0.3 }"
                class="space-y-4">
                <div v-for="(faq, index) in props.faqs" :key="index" class="rounded-xl overflow-hidden bg-white">
                    <!-- Question -->
                    <button
                        class="w-full flex justify-between items-center gap-5 
                            px-6 sm:px-8 md:px-10 2xl:px-12
                            py-4 sm:py-6 md:py-8 2xl:py-10 
                            text-left font-semibold text-primaryText 
                           text-base sm:text-[20px] md:text-[22px] 2xl:text-[28px] leading-[1.35] cursor-pointer"
                        @click="toggleFaq(index)">
                        <span>{{ faq.question }}</span>

                        <!-- icons -->
                        <span>

                            <svg v-if="openIndex === index" class="size-[26px] sm:size-[30px] md:size-[38px] 2xl:size-[44px]" viewBox="0 0 44 44" fill="none"
                                xmlns="http://www.w3.org/2000/svg">
                                <rect x="1.5" y="1.5" width="41" height="41" rx="20.5"
                                    stroke="url(#paint0_linear_2152_976)" stroke-width="3" />
                                <path
                                    d="M34 20C34.8284 20 35.5 20.6716 35.5 21.5C35.5 22.3284 34.8284 23 34 23H10C9.17157 23 8.5 22.3284 8.5 21.5C8.5 20.6716 9.17157 20 10 20H34Z"
                                    fill="url(#paint1_linear_2152_976)" />
                                <defs>
                                    <linearGradient id="paint0_linear_2152_976" x1="-3.79725" y1="0.020994" x2="29.5011"
                                        y2="41.9548" gradientUnits="userSpaceOnUse">
                                        <stop stop-color="#FF7E00" />
                                        <stop offset="1" stop-color="#FF78D7" />
                                    </linearGradient>
                                    <linearGradient id="paint1_linear_2152_976" x1="6.16987" y1="20.0014" x2="6.57801"
                                        y2="24.6274" gradientUnits="userSpaceOnUse">
                                        <stop stop-color="#FF7E00" />
                                        <stop offset="1" stop-color="#FF78D7" />
                                    </linearGradient>
                                </defs>
                            </svg>

                            <svg v-else class="size-[26px] sm:size-[30px] md:size-[38px] 2xl:size-[44px]" viewBox="0 0 44 44" fill="none"
                                xmlns="http://www.w3.org/2000/svg">
                                <rect x="1.5" y="1.5" width="41" height="41" rx="20.5"
                                    stroke="url(#paint0_linear_2150_904)" stroke-width="3" />
                                <path
                                    d="M22 8.5C22.8284 8.5 23.5 9.17157 23.5 10V20H34C34.8284 20 35.5 20.6716 35.5 21.5C35.5 22.3284 34.8284 23 34 23H23.5V34C23.5 34.8284 22.8284 35.5 22 35.5C21.1716 35.5 20.5 34.8284 20.5 34V23H10C9.17157 23 8.5 22.3284 8.5 21.5C8.5 20.6716 9.17157 20 10 20H20.5V10C20.5 9.17157 21.1716 8.5 22 8.5Z"
                                    fill="url(#paint1_linear_2150_904)" />
                                <defs>
                                    <linearGradient id="paint0_linear_2150_904" x1="-3.79725" y1="0.020994" x2="29.5011"
                                        y2="41.9548" gradientUnits="userSpaceOnUse">
                                        <stop stop-color="#FF7E00" />
                                        <stop offset="1" stop-color="#FF78D7" />
                                    </linearGradient>
                                    <linearGradient id="paint1_linear_2150_904" x1="6.16987" y1="8.51288" x2="26.6029"
                                        y2="34.245" gradientUnits="userSpaceOnUse">
                                        <stop stop-color="#FF7E00" />
                                        <stop offset="1" stop-color="#FF78D7" />
                                    </linearGradient>
                                </defs>
                            </svg>

                        </span>
                    </button>

                    <!-- Answer with smooth height transition -->
                    <transition @before-enter="(el: Element) => { (el as HTMLElement).style.height = '0px'; }" @enter="(el: Element) => {
                        (el as HTMLElement).style.transition = 'height 0.35s ease';
                        (el as HTMLElement).style.height = (el as HTMLElement).scrollHeight + 'px';
                    }" @after-enter="(el: Element) => { (el as HTMLElement).style.height = 'auto'; }" @before-leave="(el: Element) => {
                        (el as HTMLElement).style.height = (el as HTMLElement).scrollHeight + 'px';
                        (el as HTMLElement).style.transition = 'height 0.35s ease';
                    }" @leave="(el: Element) => {
                        void (el as HTMLElement).offsetHeight; /* force reflow */
                        (el as HTMLElement).style.height = '0px';
                    }">
                        <div v-show="openIndex === index" 
                            class="text-base sm:text-[20px] md:text-[22px] 2xl:text-[28px] 
                            leading-[1.35] font-medium px-6 sm:px-8 md:px-10 2xl:px-12"
                        >
                            <div class="pb-6 sm:pb-8 md:pb-10 2xl:pb-12 pr-[26px] sm:pr-[30px] md:pr-[38px] 2xl:pr-[44px]">
                                {{ faq.answer }}
                            </div>
                        </div>
                    </transition>
                </div>
            </motion.div>
        </div>
    </section>
</template>
