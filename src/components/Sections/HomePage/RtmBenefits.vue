<script setup lang="ts">
import { ref } from 'vue';
import InputField from '@/components/Ui/InputField.vue';
import PrimaryButton from '@/components/Ui/PrimaryButton.vue';
import SectionSubTitle from '@/components/Ui/SectionSubTitle.vue';
import SectionTitle from '@/components/Ui/SectionTitle.vue';
import { motion } from 'motion-v';

type FormFields = {
    firstName: string;
    lastName: string;
    email: string;
    practiceName: string;
    state: string;
    payors: string;
};

const form = ref<FormFields>({
    firstName: "",
    lastName: "",
    email: "",
    practiceName: "",
    state: "",
    payors: ""
});

const errors = ref<Record<keyof FormFields, string>>({
    firstName: "",
    lastName: "",
    email: "",
    practiceName: "",
    state: "",
    payors: ""
});

const validateForm = () => {
    let valid = true;

    (Object.keys(errors.value) as (keyof FormFields)[]).forEach((key) => {
        errors.value[key] = "";
    });

    if (!form.value.firstName) {
        errors.value.firstName = "First name is required.";
        valid = false;
    }
    if (!form.value.lastName) {
        errors.value.lastName = "Last name is required.";
        valid = false;
    }
    if (!form.value.email) {
        errors.value.email = "Work email is required.";
        valid = false;
    } else if (!/\S+@\S+\.\S+/.test(form.value.email)) {
        errors.value.email = "Enter a valid email.";
        valid = false;
    }
    if (!form.value.practiceName) {
        errors.value.practiceName = "Practice name is required.";
        valid = false;
    }
    if (!form.value.state) {
        errors.value.state = "State is required.";
        valid = false;
    }
    if (!form.value.payors) {
        errors.value.payors = "Please enter major payors.";
        valid = false;
    }

    return valid;
};

const handleSubmit = () => {
    if (validateForm()) {
        alert("Form submitted: " + JSON.stringify(form.value, null, 2));
    }
};

</script>

<template>
    <div class="w-full bg-white pt-[80px] md:pt-[200px] pb-16">
        <div class="w-full max-w-[1334px] mx-auto px-4 flex flex-col md:flex-row justify-between items-center gap-10">
            
            <motion.div 
                :initial="{ opacity: 0, y: 50 }"
                :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                :viewport="{ once: false, amount: 0.3 }"
                class="w-full md:max-w-[374px] space-y-8">
                <div class="w-full space-y-1">
                    <h3 class="text-primary text-base md:text-[20px] leading-[1.25]">
                        Download Our Free RTM Guide
                    </h3>

                    <SectionTitle>
                        Discover the Benefits of RTM
                    </SectionTitle>

                    <SectionSubTitle>
                        Learn how to implement RTM in your practice, navigate billing, and provide better care for your
                        patients.
                    </SectionSubTitle>
                </div>

                <form @submit.prevent="handleSubmit" class="w-full space-y-4">
                    <InputField v-model="form.firstName" label="First Name" name="firstName"
                        :error="errors.firstName" />

                    <InputField v-model="form.lastName" label="Last Name" name="lastName" :error="errors.lastName" />

                    <InputField v-model="form.email" label="Work Email" name="email" type="email"
                        :error="errors.email" />

                    <InputField v-model="form.practiceName" label="Practice Name" name="practiceName"
                        :error="errors.practiceName" />

                    
                    <PrimaryButton primary-type="button" @click="handleSubmit" text="Submit" extra-class="min-w-[140px]" />
                </form>
            </motion.div>

            <motion.div 
                :initial="{ opacity: 0, y: 50 }"
                :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                :viewport="{ once: false, amount: 0.3 }"
                class="md:max-w-[816px] w-full">
                <img src="/images/RtmBenifiteBanner.webp" alt="banner" class="w-full">
            </motion.div>
        </div>
    </div>
</template>