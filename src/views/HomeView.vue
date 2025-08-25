<script setup lang="ts">
import CptCode from '@/components/Sections/HomePage/CptCode.vue';
import HomeHero from '@/components/Sections/HomePage/HomeHero.vue';
import Marquee from '@/components/Ui/Marquee.vue';
import RoiCalculator from '@/components/Sections/HomePage/RoiCalculator.vue';
import RtmFrom from '@/components/Sections/HomePage/RtmFrom.vue';
import RtmBenefits from '@/components/Sections/HomePage/RtmBenefits.vue';
import GrowthPartner from '@/components/Sections/HomePage/GrowthPartner.vue';
import PhyxUpHealth from '@/components/Sections/HomePage/PhyxUpHealth.vue';
import ProvenResult from '@/components/Sections/HomePage/ProvenResult.vue';
import TrustedBy from '@/components/Sections/HomePage/TrustedBy.vue';
import SmartMonitoring2 from '@/components/Sections/HomePage/SmartMonitoring2.vue';
import Blog from '@/components/Sections/HomePage/Blog.vue';
import Faq from '@/components/Sections/HomePage/Faq.vue';
import { motion } from 'motion-v';

</script>

<template>
  <main>
    <HomeHero />

    <motion.div 
      :initial="{ opacity: 0, y: 50 }"
      :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
      :viewport="{ once: false, amount: 0.3 }"
      class="py-14 xl:py-16 2xl:py-[100px]">
      <Marquee />
    </motion.div>

    <CptCode />

    <RtmFrom />
    
    <RoiCalculator />
    <SmartMonitoring2 />

    <RtmBenefits />

    <GrowthPartner />

    <PhyxUpHealth />
    
    <ProvenResult />
    <TrustedBy />
    <Blog />

    <Faq :faqs="[
        { question: 'How does PhyxUp Health help with billing and reimbursement for RTM?', answer: 'We track monitoring time, manage billing, and streamline workflows so you get reimbursed faster.' },
        { question: 'How can PhyxUp Health help increase reimbursement for RTM?', answer: 'PhyxUp Health makes it easy to increase RTM reimbursement by cutting down the work for clinicians. Our system automatically tracks monitoring time, updates home exercise programs, and keeps up with patient progress, so you can provide RTM to more patients without adding extra admin work. Since everything is logged and organized for billing, you can confidently submit more claims without worrying about missed details. In the end, you get paid more for the care you’re already providing, with way less effort.' },
        { question: 'How easy is it to integrate PhyxUp Health into my practice?', answer: 'Super easy. No complex setup. Just plug in and start using.' },
        { question: 'Can PhyxUp Health integrate with my EHR or other software?', answer: 'Yes, we integrate with most EHR systems seamlessly.' }
      ]" 
    />


  </main>
</template>
