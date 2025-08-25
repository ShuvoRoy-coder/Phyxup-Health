<script setup lang="ts">
// interface for props
interface SecondaryButtonProps {
  text?: string
  extraClass?: string
  secondaryType?: "button" | "link"
  to?: string // for link navigation
}

// define props
const props = defineProps<SecondaryButtonProps>()

// define emits
const emit = defineEmits<{
  (e: "click"): void
}>()
</script>

<template>
  <!-- Button -->
  <button
    v-if="props.secondaryType === 'button'"
    class="text-black font-semibold text-[16px] leading-[22px] text-center 
      inline-flex items-center justify-center gap-1 rounded-[8px] xl:rounded-2xl px-4 py-3 font-mont bg-white cursor-pointer
      border border-bdr
      transition-all duration-300 hover:bg-SecondaryHv"
    :class="props.extraClass"
    @click="emit('click')"
  >
    <span v-if="props.text">
      {{ props.text }}
    </span>
    <slot />
  </button>

  <!-- Router Link -->
  <RouterLink
    v-else-if="props.secondaryType === 'link'"
    :to="props.to || '/'"
    class="text-black font-semibold text-[16px] leading-[22px] text-center 
      inline-flex items-center justify-center gap-1 rounded-[8px] xl:rounded-2xl px-4 py-3 font-mont bg-white cursor-pointer
      border border-bdr
      transition-all duration-300 hover:bg-SecondaryHv"
    :class="props.extraClass"
  >
    <span v-if="props.text">
      {{ props.text }}
    </span>
    <slot />
  </RouterLink>
</template>
