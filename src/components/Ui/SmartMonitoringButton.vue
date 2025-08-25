<script setup lang="ts">
// interface for props
interface SmartMonitoringButton {
    extraClass?: string
    active?: boolean
}

// define props
const props = defineProps<SmartMonitoringButton>()

// define emits
const emit = defineEmits<{
    (e: "click"): void
}>()
</script>

<template>
  <div
    class="relative w-full after:bg-primary after:absolute after:w-full after:h-full after:z-0 after:transition-all after:duration-300 after:left-0 after:rounded-[5px]"
    :class="[
      props.active
        ? 'after:opacity-100 after:-bottom-[5%]'
        : 'after:opacity-0 after:bottom-0 hover:after:-bottom-[5%] hover:after:opacity-100'
    ]"
  >
    <button
      class="relative z-10 w-full cursor-pointer bg-white rounded-[5px] border border-bdr inline-flex items-center justify-center gap-2
        px-3 py-6 text-base sm:text-xl md:py-[4.3cqw] md:px-[0.8cqw] text-black md:text-[1.8cqw]
        transition-all duration-300 hover:bg-SecondaryHv"
      :class="props.extraClass"
      @click="emit('click')"
    >
      <slot />
    </button>
  </div>
</template>
