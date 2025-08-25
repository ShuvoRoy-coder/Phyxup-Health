<script setup lang="ts">
// interface for props
interface SectionTitle {
    extraClass?: string
}

// define props
const props = defineProps<SectionTitle>()

</script>


<template>
    <div class="font-inter text-primaryText font-medium 
         leading-[1.25] tracking-[-1px]
         text-[22px] sm:text-[30px] md:text-[40px] 2xl:text-[56px]" 
         :class="props.extraClass"
    >
        <slot />
    </div>
</template>