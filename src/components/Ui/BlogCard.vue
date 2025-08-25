<script setup lang="ts">
import { defineProps } from "vue";

// Define interface for props
interface BlogCardProps {
  image: string;
  readTime?: string;
  title: string;
}

// Use interface in defineProps
const props = defineProps<BlogCardProps>();
</script>

<template>
  <div class="space-y-[20px]">
    <!-- image part -->
    <div
      class="bg-[linear-gradient(135deg,rgba(255,126,0,1)_0%,rgba(255,120,215,1)_100%)]
             w-full rounded-2xl overflow-hidden p-[2px]"
    >
      <div class="w-full h-full rounded-[14px] overflow-hidden">
        <img :src="props.image" alt="blog-img" class="w-full h-full object-cover" />
      </div>
    </div>

    <!-- text part -->
    <div class="text-primaryText space-y-[8px]">
      <div class="text-base font-medium">
        {{ props.readTime ?? "5 min read" }}
      </div>
      <div class="font-semibold text-base sm:text-[18px] md:text-[20px] lg:text-[24px] leading-[1.5] tracking-[0.05px]">
        {{ props.title }}
      </div>
    </div>
  </div>
</template>
