<script setup lang="ts">
import { defineProps, defineEmits, computed } from "vue";

interface RangeInputProps {
  code?: string;
  price?: string;
  min: number;
  max: number;
  step?: number;
  modelValue: number;
}

const props = defineProps<RangeInputProps>();
const emit = defineEmits(["update:modelValue"]);

// Calculate background gradient fill
const sliderStyle = computed(() => {
  const min = props.min ?? 0;
  const max = props.max ?? 100;
  const val = ((props.modelValue - min) / (max - min)) * 100;
  return {
    background: `linear-gradient(to right, #FF7E00 ${val}%, #DBDBDB ${val}%)`
  };
});

</script>

<template>
  <div class="flex flex-col gap-2 w-full">

    <div class="w-full flex items-start gap-2">

      <div v-if="props.max < 10" class="flex items-center gap-2">
        <div class="text-black leading-[1.25] text-xs sm:text-base">
          {{ price }}
        </div>
        <div class="border border-black px-2 py-1 sm:px-3 sm:py-2 rounded-full text-black leading-[1.25] font-bold text-xs sm:text-base">
          {{ code }}
        </div>
      </div>

      <!-- Range slider -->
      <div class="w-full space-y-3 sm:mt-1">
        <input type="range" class="w-full slider" :min="min ?? 0" :max="max ?? 100" :step="step ?? 1" :value="modelValue"
          :style="sliderStyle" @input="emit('update:modelValue', +($event.target as HTMLInputElement).value)" />
        <!-- Value labels under slider -->
        <div v-if="props.max < 10" class="flex justify-between text-xs sm:text-sm text-black w-full">
          <span v-for="i in (max ?? 100) - (min ?? 0) + 1" :key="i">
            {{ (min ?? 0) + (i - 1) }}
          </span>
        </div>
      </div>

      <div class="border border-bdr px-1.5 py-1 sm:px-3 sm:py-2 shrink-0 min-w-8 sm:min-w-12 flex text-center items-center justify-center text-xs sm:text-base">
        {{ modelValue }}
      </div>

    </div>
  </div>
</template>

<style>
.slider {
  -webkit-appearance: none;
  appearance: none;
  width: 100%;
  height: 8px;
  border-radius: 1px;
  outline: none;
  cursor: pointer;
}

/* Thumb styling */
.slider::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 16px;
  height: 24px;
  background: #FF7E00;
  border-radius: 4px;
  cursor: pointer;
}

.slider::-moz-range-thumb {
  width: 16px;
  height: 24px;
  background: #FF7E00;
  border-radius: 4px;
  cursor: pointer;
}
</style>
