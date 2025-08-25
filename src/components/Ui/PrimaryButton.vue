<script setup lang="ts">
// interface for props
interface PrimaryButtonProps {
  text: string
  extraClass?: string
  primaryType?: "button" | "link"
  to?: string // for link
}

// define props
const props = defineProps<PrimaryButtonProps>()

// define emits
const emit = defineEmits<{
  (e: "click"): void
}>()
</script>

<template>
  <!-- If type is button -->
  <button
    v-if="props.primaryType === 'button'"
    class="text-white font-semibold text-[16px] leading-[22px] text-center 
      inline-flex items-center justify-center gap-2.5 rounded-[8px] xl:rounded-2xl px-4 py-3 font-mont bg-primary cursor-pointer
      transition-all duration-300 hover:bg-primaryHv"
    :class="props.extraClass"
    @click="emit('click')"
  >
    {{ props.text }}
    <slot/>
  </button>

  <!-- If type is link -->
  <RouterLink
    v-else-if="props.primaryType === 'link'"
    :to="props.to || '/'"
    class="text-white font-semibold text-[16px] leading-[22px] text-center 
      inline-flex items-center justify-center gap-2.5 rounded-[8px] xl:rounded-2xl px-4 py-3 font-mont bg-primary cursor-pointer
      transition-all duration-300 hover:bg-primaryHv"
    :class="props.extraClass"
  >
    {{ props.text }}
    <slot/>
  </RouterLink>
</template>
