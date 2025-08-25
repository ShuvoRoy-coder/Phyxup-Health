<script setup lang="ts">
// interface for props
interface SectionTitle {
    extraClass?: string
}

// define props
const props = defineProps<SectionTitle>()

</script>


<template>
    <div class="font-mont text-primaryText font-medium leading-[1.25]
         text-[14px] sm:text-[16px] md:text-[18px] 2xl:text-[22px]"
          :class="props.extraClass"
    >
        <slot />
    </div>
</template>