<script setup lang="ts">
import { onMounted, onUnmounted, ref } from "vue";
import { RouterView } from "vue-router";
import Navbar from "./components/Navbar.vue";
import FooterSection from "./components/FooterSection.vue";
import { motion } from "motion-v";

const isScrolled = ref(false);

const handleScroll = () => {
  // once scrolled more than 65px → remove padding
  isScrolled.value = window.scrollY > 65;
};

onMounted(() => {
  window.addEventListener("scroll", handleScroll);
});

onUnmounted(() => {
  window.removeEventListener("scroll", handleScroll);
});
</script>

<template>
  <div class="font-mont">
    <!-- navbar area -->
    <div
      class="fixed left-0 top-0 z-50 w-full transition-all duration-300"
      :class="isScrolled ? 'pt-3 2xl:pt-10' : 'pt-6 xl:pt-10 2xl:pt-[65px]'"
    >
      <Navbar />
    </div>
    
    <RouterView />

    <FooterSection/>
    
  </div>
</template>
