<script setup lang="ts">
import BlogCard from '@/components/Ui/BlogCard.vue';
import PrimaryButton from '@/components/Ui/PrimaryButton.vue';
import SectionTitle from '@/components/Ui/SectionTitle.vue';
import TernaryButton from '@/components/Ui/TernaryButton.vue';
import { motion } from 'motion-v';

</script>

<template>
    <div class="w-full bg-sectionBg1 px-4 py-10 md:py-16">
        <div class="max-w-[1296px] mx-auto">

            <motion.div 
                :initial="{ opacity: 0, y: 50 }"
                :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                :viewport="{ once: false, amount: 0.3 }"
                class="w-full space-y-5 text-center">
                <TernaryButton ternary-type="link" to="/" extra-class="min-w-[55px]">
                    Blog
                </TernaryButton>
                <SectionTitle extra-class="text-center">
                    Explore Additional Resources
                </SectionTitle>
            </motion.div>

            <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-10 py-6 md:py-10">
                <motion.div :initial="{ opacity: 0, y: 50 }"
                    :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                    :viewport="{ once: false, amount: 0.3 }">
                    <BlogCard image="/images/blogImg1.webp" readTime="5 min read"
                    title="What is Remote Therapeutic Monitoring (RTM)? A Guide for Physical Therapy Clinics" />
                </motion.div>

                <motion.div
                    :initial="{ opacity: 0, y: 50 }"
                    :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                    :viewport="{ once: false, amount: 0.3 }"
                >
                    <BlogCard image="/images/blogImg2.webp" readTime="5 min read"
                    title="Losing Revenue to No Shows? Here’s How RTM Helps Physical Therapy Clinics Recover" />
                </motion.div>
                    
                <motion.div
                    :initial="{ opacity: 0, y: 50 }"
                    :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                    :viewport="{ once: false, amount: 0.3 }"
                >
                    <BlogCard image="/images/blogImg3.webp" readTime="4 min read"
                    title="Why Patients Skip Home Exercises, And How Remote Therapeutic Monitoring Fixes It" />
                </motion.div>

            </div>

            <motion.div 
                :initial="{ opacity: 0, y: 50 }"
                :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                :viewport="{ once: false, amount: 0.3 }"
                class="text-center">
                <PrimaryButton primary-type="link" text="See More" extra-class="min-w-[172px]"/>
            </motion.div>

        </div>
    </div>
</template>