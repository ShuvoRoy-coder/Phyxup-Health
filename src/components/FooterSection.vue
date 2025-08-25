<script setup lang="ts">
import { ref } from "vue";
import PrimaryButton from "./Ui/PrimaryButton.vue";
import { motion } from "motion-v";

// email state
const email = ref("");

// submit handler
const handleSubscribe = () => {
    if (!email.value) return;
    // Normally you would call API here
    console.log("Subscribed with:", email.value);
    email.value = "";
};
</script>

<template>
    <footer class="bg-sectionBg1 px-4">
        <div class="max-w-[1550px] mx-auto border-t border-primary">
            <div class="max-w-[1185px] mx-auto py-12 lg:py-16 grid grid-cols-1 md:grid-cols-2 gap-10 items-center">
                <!-- Left Section -->
                <motion.div
                    :initial="{ opacity: 0, y: 50 }"
                    :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                    :viewport="{ once: false, amount: 0.3 }" 
                    class="space-y-5">
                    <!-- Logo + Socials -->
                    <div class="flex items-center space-x-4">

                        <RouterLink to="/" class="max-w-[130px] md:max-w-[180px] w-full">
                            <img src="/logos/phyxcp-health.webp" alt="logo" class="w-full mt-1">
                        </RouterLink>

                        <!-- social icons -->
                        <a href="#" aria-label="YouTube"
                            class="shrink-0 size-10 bg-white rounded-full inline-flex items-center justify-center transition-all duration-300 hover:bg-bdr">
                            <svg width="20" height="15" viewBox="0 0 20 15" fill="none"
                                xmlns="http://www.w3.org/2000/svg">
                                <path
                                    d="M19.4422 2.552C19.2572 1.532 18.3762 0.788 17.3542 0.556C15.8242 0.232 12.9932 0 9.92924 0C6.86824 0 3.99124 0.232 2.45924 0.556C1.43924 0.788 0.556242 1.484 0.372242 2.552C0.118147 4.16344 -0.00625183 5.79266 0.000241618 7.424C0.000241618 9.512 0.185242 11.137 0.417242 12.297C0.604242 13.317 1.48524 14.06 2.50524 14.292C4.12924 14.617 6.91324 14.849 9.97624 14.849C13.0402 14.849 15.8242 14.617 17.4482 14.292C18.4682 14.06 19.3492 13.364 19.5362 12.296C19.7212 11.136 19.9532 9.466 20.0002 7.424C19.9062 5.336 19.6742 3.712 19.4422 2.552ZM7.42424 10.672V4.176L13.0852 7.424L7.42424 10.672Z"
                                    fill="#CE1312" />
                            </svg>
                        </a>

                        <a href="#" aria-label="LinkedIn"
                            class="shrink-0 size-10 bg-white rounded-full inline-flex items-center justify-center transition-all duration-300 hover:bg-bdr">
                            <svg width="16" height="16" viewBox="0 0 16 16" fill="none"
                                xmlns="http://www.w3.org/2000/svg">
                                <path
                                    d="M3.596 15.99H0.24V5.32997H3.596V15.99ZM1.916 3.85397C1.53527 3.8518 1.16371 3.73688 0.848223 3.52374C0.532737 3.31059 0.287463 3.00876 0.143358 2.65635C-0.000747934 2.30393 -0.0372258 1.91673 0.0385277 1.5436C0.114281 1.17047 0.298871 0.828145 0.568999 0.559828C0.839128 0.291512 1.18269 0.109231 1.55632 0.0359901C1.92995 -0.0372505 2.3169 0.00183283 2.66833 0.148307C3.01977 0.294781 3.31994 0.542081 3.53096 0.858994C3.74198 1.17591 3.85439 1.54823 3.854 1.92897C3.8574 2.18381 3.80951 2.43673 3.71315 2.67267C3.6168 2.90861 3.47396 3.12276 3.29314 3.30237C3.11232 3.48198 2.89722 3.62337 2.66063 3.71813C2.42404 3.81289 2.17081 3.85909 1.916 3.85397ZM15.966 16H12.61V10.176C12.61 8.45897 11.88 7.92897 10.938 7.92897C9.943 7.92897 8.966 8.67897 8.966 10.219V16H5.611V5.33797H8.839V6.81597H8.882C9.206 6.15997 10.341 5.03897 12.072 5.03897C13.945 5.03897 15.968 6.15097 15.968 9.40597L15.966 16Z"
                                    fill="#0A66C2" />
                            </svg>
                        </a>
                    </div>

                    <!-- Address -->
                    <p class="text-primaryText text-base font-poopins">San Jose, California</p>

                    <!-- Email -->
                    <div class="flex items-center space-x-2 text-gray-700">
                        <svg width="20" height="16" viewBox="0 0 20 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path
                                d="M20 2C20 0.9 19.1 0 18 0H2C0.9 0 0 0.9 0 2V14C0 15.1 0.9 16 2 16H18C19.1 16 20 15.1 20 14V2ZM18 2L10 7L2 2H18ZM18 14H2V4L10 9L18 4V14Z"
                                fill="#1F222C" />
                        </svg>
                        <a href="mailto:support@phyxuphealth.com" class="hover:underline font-poppins text-primaryText">
                            support@phyxuphealth.com
                        </a>
                    </div>
                </motion.div>

                <!-- Right Section -->
                <motion.div
                    :initial="{ opacity: 0, y: 50 }"
                    :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                    :viewport="{ once: false, amount: 0.3 }" 
                    class="space-y-2 text-primaryText">
                    <p class="text-xs uppercase font-semibold font-mont">
                        View our free RTM guide
                    </p>
                    <h3 class="text-[32px] leading-[1.5] tracking-[-1px] font-semibold font-inter">
                        Discover the Benefits of RTM
                    </h3>
                    <p class="text-base font-medium">
                        Learn how to implement RTM in your practice, navigate billing, and provide
                        better care for your patients.
                    </p>

                    <!-- Subscribe form -->
                    <form @submit.prevent="handleSubscribe"
                        class="flex w-full max-w-[480px] mt-6 px-2 py-1 bg-white shadow-xl rounded-[8px] xl:rounded-2xl overflow-hidden">
                        <input v-model="email" type="email" placeholder="Email"
                            class="w-full px-4 py-2 text-sm outline-none rounded-l-full" />


                        <PrimaryButton primary-type="button" text="Subscribe" extra-class="min-w-[120px] sm:min-w-[160px] lg:min-w-[191px]"/>

                    </form>
                </motion.div>
            </div>

            <!-- Bottom bar -->
            <motion.div
                :initial="{ opacity: 0, y: 50 }"
                :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                :viewport="{ once: false, amount: 0.3 }"
                class="text-sm text-primaryText grid 
                   grid-cols-1 sm:grid-cols-3 md:grid-cols-4 max-w-[1016px] w-full mx-auto gap-4 py-10 text-center">
                <p class="sm:col-span-3 md:col-span-1">© 2025 PhyxUp Health, Inc.</p>
                <a href="#" class="hover:underline inline-flex items-center justify-center">Terms of Service</a>
                <a href="#" class="hover:underline inline-flex items-center justify-center">Privacy Policy</a>
                <a href="#" class="hover:underline inline-flex items-center justify-center">All Rights Reserved</a>
            </motion.div>
        </div>
    </footer>
</template>
