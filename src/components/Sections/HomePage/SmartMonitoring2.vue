<script setup lang="ts">
import SectionSubTitle from '@/components/Ui/SectionSubTitle.vue';
import SectionTitle from '@/components/Ui/SectionTitle.vue';
import SmartMonitoringButton from '@/components/Ui/SmartMonitoringButton.vue';
import { motion, useScroll, useMotionValueEvent } from 'motion-v';
import { ref } from 'vue';

const videos = [
    { id: 0, label: "AI MONITORING", src: "https://www.w3schools.com/tags/movie.mp4" },
    { id: 1, label: "AI RECOMMENDATION", src: "https://www.w3schools.com/tags/movie.mp4" },
    { id: 2, label: "BILLING & REIMBURSEMENT", src: "https://www.w3schools.com/tags/movie.mp4" }
];

const sectionRef = ref<HTMLElement | null>(null);
const activeVideo = ref(0);
let isClickScrolling = false;
let targetIndex: number | null = null;

// pin scroll effect
const { scrollYProgress } = useScroll({
    target: sectionRef,
    offset: ["start start", "end end"], // full section pinned
});

function scrollToSection(index: number) {
    if (!sectionRef.value) return;

    isClickScrolling = true;
    targetIndex = index;
    activeVideo.value = index; // update button immediately

    const rect = sectionRef.value.getBoundingClientRect();
    const scrollTop = window.scrollY + rect.top;
    const sectionHeight = rect.height - window.innerHeight;
    const target = scrollTop + (sectionHeight * (index / (videos.length - 1)));

    window.scrollTo({ top: target, behavior: "smooth" });
}

// scroll watcher
useMotionValueEvent(scrollYProgress, "change", (latest) => {
    if (isClickScrolling) {
        // wait until we are "close enough" to target
        if (targetIndex === 0 && latest < 0.05) {
            isClickScrolling = false;
            targetIndex = null;
        } else if (targetIndex === 1 && latest > 0.33 && latest < 0.66) {
            isClickScrolling = false;
            targetIndex = null;
        } else if (targetIndex === 2 && latest > 0.95) {
            isClickScrolling = false;
            targetIndex = null;
        }
        return;
    }

    // normal scroll updates
    if (latest < 0.33) activeVideo.value = 0;
    else if (latest < 0.66) activeVideo.value = 1;
    else activeVideo.value = 2;
});




</script>

<template>
    <!-- Outer wrapper creates the "scroll room" -->
    <section class="w-full">
        <!-- Inner content is pinned -->
        <div class="bg-sectionBg1">
            <motion.div :initial="{ opacity: 0, y: 50 }"
                :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                :viewport="{ once: false, amount: 0.3 }" class="max-w-[1750px] mx-auto px-4 sm:px-10 xl:px-20 w-full">
                <!-- Heading -->
                <SectionTitle extra-class="text-center">
                    Smart Monitoring That Drives Growth
                </SectionTitle>

                <div ref="sectionRef" class="relative min-h-[300vh]">
                    <div class="sticky top-0 h-screen">

                        <motion.div :initial="{ opacity: 0, y: 50 }"
                            :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                            :viewport="{ once: false, amount: 0.3 }"
                            class="grid grid-cols-1 lg:grid-cols-3 gap-4 lg:gap-8 h-full overflow-hidden pt-3 md:pt-0 lg:pt-12 2xl:pt-20">
                            <!-- Left Text -->
                            <div class="space-y-4 h-full lg:max-h-[776px] flex flex-col items-start justify-center">
                                <h3 class="text-primary text-base md:text-[20px] leading-[1.25]">
                                    How PhyxUp Health Works
                                </h3>
                                <SectionTitle>AI-Assisted Monitoring Between Visits</SectionTitle>
                                <div class="w-full h-1 bg-primary rounded-full"></div>
                                <SectionSubTitle>
                                    AI tracks patient activity and recovery trends between appointments,
                                    predicts likely outcomes, and flags concerns before they impact progress.
                                </SectionSubTitle>
                            </div>

                            <!-- Right Video -->
                            <div
                                class=" flex flex-col items-center lg:items-start gap-3 sm:gap-5 2xl:gap-10 w-full h-auto lg:h-full relative @container col-span-1 lg:col-span-2 pb-4">
                                <div class="rounded-2xl shadow-xl overflow-hidden max-w-[450px] w-full lg:max-w-[100%] lg:w-auto lg:h-full lg:max-h-[776px] mx-auto
                                        bg-[url('/images/videoplayerBg.webp')] bg-cover bg-no-repeat bg-center">
                                    <div class="w-full h-full sm:px-[18px] sm:py-[20px] lg:px-[28px] lg:py-[30px]">
                                        <div
                                            class="rounded-2xl h-full py-4 px-4 md:py-4 md:px-[18px] overflow-hidden sm:bg-white/20">
                                            <!-- Video transition -->
                                            <motion.div :key="videos[activeVideo].id"
                                                :initial="{ opacity: 0, scale: 0.95 }"
                                                :animate="{ opacity: 1, scale: 1 }" :exit="{ opacity: 0, scale: 0.95 }"
                                                :transition="{ duration: 0.6, ease: 'easeOut' }"
                                                class="relative rounded-2xl p-3 md:p-4 bg-white h-full overflow-hidden">
                                                <video :src="videos[activeVideo].src" loop muted playsinline controls
                                                    autoplay class="aspect-video h-full object-cover w-full">
                                                </video>

                                                <!-- <div class="absolute w-full bg-red-300 top-0 left-0">
                                                    {{ videos[activeVideo].id }}
                                                </div> -->
                                            </motion.div>
                                        </div>
                                    </div>
                                </div>

                                <!-- Bottom Buttons -->
                                <motion.div :initial="{ opacity: 0, y: 50 }"
                                    :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                                    :viewport="{ once: false, amount: 0.3 }" class="w-full">
                                    <div
                                        class="flex flex-col sm:flex-row items-center gap-[6px] sm:gap-[2.3cqw] w-full">
                                        <SmartMonitoringButton v-for="(video, index) in videos" :key="video.id"
                                            :active="activeVideo === index" @click="scrollToSection(index)">
                                            <span>{{ video.label }}</span>

                                            <svg v-if="index=== 0" class="size-[25px] sm:size-[3cqw]"
                                                viewBox="0 0 27 28" fill="none" xmlns="http://www.w3.org/2000/svg">
                                                <path
                                                    d="M14.7393 10L18.7393 14L14.7393 18M8.07302 10L12.073 14L8.07302 18"
                                                    stroke="#344054" stroke-width="2.5" stroke-linecap="round"
                                                    stroke-linejoin="round" />
                                                <path
                                                    d="M24.0731 2L2.73937 2C2.00337 2 1.40625 2.59712 1.40625 3.33312L1.40625 24.6669C1.40625 25.4029 2.00337 26 2.73937 26L24.0731 26C24.8091 26 25.4062 25.4029 25.4062 24.6669L25.4062 3.33312C25.4062 2.59712 24.8091 2 24.0731 2Z"
                                                    stroke="#FF7E00" stroke-width="2.5" stroke-linecap="round"
                                                    stroke-linejoin="round" />
                                            </svg>

                                            <svg v-if="index=== 1" class="size-[25px] sm:size-[3cqw]"
                                                viewBox="0 0 29 32" fill="none" xmlns="http://www.w3.org/2000/svg">
                                                <path
                                                    d="M6.90625 22C6.90625 21.4696 7.11696 20.9609 7.49204 20.5858C7.86711 20.2107 8.37582 20 8.90625 20C9.43668 20 9.94539 20.2107 10.3205 20.5858C10.6955 20.9609 10.9062 21.4696 10.9062 22V24C10.9062 24.5304 10.6955 25.0391 10.3205 25.4142C9.94539 25.7893 9.43668 26 8.90625 26C8.37582 26 7.86711 25.7893 7.49204 25.4142C7.11696 25.0391 6.90625 24.5304 6.90625 24V22ZM18.9062 14C18.9062 13.4696 19.117 12.9609 19.492 12.5858C19.8671 12.2107 20.3758 12 20.9062 12C21.4367 12 21.9454 12.2107 22.3205 12.5858C22.6955 12.9609 22.9062 13.4696 22.9062 14V24C22.9062 24.5304 22.6955 25.0391 22.3205 25.4142C21.9454 25.7893 21.4367 26 20.9062 26C20.3758 26 19.8671 25.7893 19.492 25.4142C19.117 25.0391 18.9062 24.5304 18.9062 24V14ZM12.9062 18C12.9062 17.4696 13.117 16.9609 13.492 16.5858C13.8671 16.2107 14.3758 16 14.9062 16C15.4367 16 15.9454 16.2107 16.3205 16.5858C16.6955 16.9609 16.9062 17.4696 16.9062 18V24C16.9062 24.5304 16.6955 25.0391 16.3205 25.4142C15.9454 25.7893 15.4367 26 14.9062 26C14.3758 26 13.8671 25.7893 13.492 25.4142C13.117 25.0391 12.9062 24.5304 12.9062 24V18Z"
                                                    fill="#344054" />
                                                <path
                                                    d="M6.90625 3H4.90625C3.84538 3 2.82797 3.42143 2.07782 4.17157C1.32768 4.92172 0.90625 5.93913 0.90625 7V28C0.90625 29.0609 1.32768 30.0783 2.07782 30.8284C2.82797 31.5786 3.84538 32 4.90625 32H24.9062C25.9671 32 26.9845 31.5786 27.7347 30.8284C28.4848 30.0783 28.9062 29.0609 28.9062 28V7C28.9062 5.93913 28.4848 4.92172 27.7347 4.17157C26.9845 3.42143 25.9671 3 24.9062 3H22.9062V5H24.9062C25.4367 5 25.9454 5.21071 26.3205 5.58579C26.6955 5.96086 26.9062 6.46957 26.9062 7V28C26.9062 28.5304 26.6955 29.0391 26.3205 29.4142C25.9454 29.7893 25.4367 30 24.9062 30H4.90625C4.37582 30 3.86711 29.7893 3.49204 29.4142C3.11696 29.0391 2.90625 28.5304 2.90625 28V7C2.90625 6.46957 3.11696 5.96086 3.49204 5.58579C3.86711 5.21071 4.37582 5 4.90625 5H6.90625V3Z"
                                                    fill="#FF7E00" />
                                                <path
                                                    d="M17.9062 2C18.1715 2 18.4258 2.10536 18.6134 2.29289C18.8009 2.48043 18.9062 2.73478 18.9062 3V5C18.9062 5.26522 18.8009 5.51957 18.6134 5.70711C18.4258 5.89464 18.1715 6 17.9062 6H11.9062C11.641 6 11.3867 5.89464 11.1991 5.70711C11.0116 5.51957 10.9062 5.26522 10.9062 5V3C10.9062 2.73478 11.0116 2.48043 11.1991 2.29289C11.3867 2.10536 11.641 2 11.9062 2H17.9062ZM11.9062 0C11.1106 0 10.3475 0.31607 9.78493 0.87868C9.22232 1.44129 8.90625 2.20435 8.90625 3V5C8.90625 5.79565 9.22232 6.55871 9.78493 7.12132C10.3475 7.68393 11.1106 8 11.9062 8H17.9062C18.7019 8 19.465 7.68393 20.0276 7.12132C20.5902 6.55871 20.9062 5.79565 20.9062 5V3C20.9062 2.20435 20.5902 1.44129 20.0276 0.87868C19.465 0.31607 18.7019 0 17.9062 0L11.9062 0Z"
                                                    fill="#FF7E00" />
                                            </svg>

                                            <svg v-if="index=== 2" class="size-[25px] sm:size-[3cqw]"
                                                viewBox="0 0 27 28" fill="none" xmlns="http://www.w3.org/2000/svg">
                                                <path
                                                    d="M1.40625 12.6668H9.40625M14.7394 13.9999L16.1928 15.6664L18.74 12.3333M2.73937 7.33301H9.40625V20.6668H2.73937C2.56425 20.6668 2.39084 20.6323 2.22906 20.5652C2.06728 20.4982 1.92029 20.3999 1.79649 20.2761C1.67269 20.1522 1.5745 20.0052 1.50754 19.8434C1.44059 19.6816 1.40617 19.5081 1.40625 19.333V8.66677C1.40625 8.31314 1.54668 7.97399 1.79667 7.72388C2.04666 7.47377 2.38575 7.33318 2.73937 7.33301Z"
                                                    stroke="#344054" stroke-width="2.5" stroke-linecap="round"
                                                    stroke-linejoin="round" />
                                                <path
                                                    d="M25.4062 24.6669V3.33312C25.4062 2.97955 25.2658 2.64047 25.0158 2.39046C24.7658 2.14045 24.4267 2 24.0731 2H10.7394C10.3858 2 10.0467 2.14045 9.79671 2.39046C9.5467 2.64047 9.40625 2.97955 9.40625 3.33312V24.6669C9.40625 25.0204 9.5467 25.3595 9.79671 25.6095C10.0467 25.8595 10.3858 26 10.7394 26H24.0731C24.4267 26 24.7658 25.8595 25.0158 25.6095C25.2658 25.3595 25.4062 25.0204 25.4062 24.6669ZM15.4062 4.66688H19.4062L20.0731 2H14.7394L15.4062 4.66688Z"
                                                    stroke="#FF7E00" stroke-width="2.5" stroke-linecap="round"
                                                    stroke-linejoin="round" />
                                            </svg>

                                        </SmartMonitoringButton>
                                    </div>
                                </motion.div>
                            </div>
                        </motion.div>


                    </div>
                </div>
            </motion.div>
        </div>
        <svg class="max-w-[1663px] mx-auto rotate-180 -translate-y-1" viewBox="0 0 1663 127" fill="none"
            xmlns="http://www.w3.org/2000/svg">
            <path d="M831.384 0L1662.77 126.809H0L831.384 0Z" fill="#FEF8ED" />
        </svg>

    </section>
</template>
