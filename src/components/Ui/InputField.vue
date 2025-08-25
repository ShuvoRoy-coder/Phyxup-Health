<script setup lang="ts">
import { defineProps } from "vue";

interface InputFieldProps {
    modelValue: string;
    label: string;
    name: string;
    type?: string;
    error?: string;
    placeholder?: string;
}

const props = defineProps<InputFieldProps>();
const emit = defineEmits(["update:modelValue"]);
</script>

<template>
    <div class="flex flex-col">
        <!-- Label -->
        <label :for="name" class="text-base font-medium text-primaryText mb-1">
            {{ label }}
        </label>

        <!-- Input -->
        <input :id="name" :name="name" :type="type || 'text'" :placeholder="placeholder" 
            class="w-full rounded-md border px-3 py-2 focus:outline-none focus:ring-2
             focus:ring-primary border-bdr text-primaryText bg-white" 
            :class="error ? 'border-red-500' : 'border-gray-300'"
            :value="modelValue" @input="emit('update:modelValue', ($event.target as HTMLInputElement).value)" />

        <!-- Error -->
        <span v-if="error" class="text-sm text-red-500 mt-1">{{ error }}</span>
    </div>
</template>
