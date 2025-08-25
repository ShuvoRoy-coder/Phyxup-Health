<script setup lang="ts">
import { RouterLink } from 'vue-router';

interface LinkProps {
    text: string
    url: string
}

defineProps<LinkProps>()

</script>

<template>
    <RouterLink :to="url"
        class="py-2 xl:py-4 inline-block text-center text-[16px] leading-[22px] font-semibold relative after:bg-black after:absolute after:w-0 hover:after:w-full after:transition-all after:duration-300 after:h-0.5 after:bottom-0 after:left-0">
        {{ text }}
    </RouterLink>
</template>