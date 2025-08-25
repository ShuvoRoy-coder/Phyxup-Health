<script setup lang="ts">
import { ref } from 'vue';
import SectionSubTitle from '@/components/Ui/SectionSubTitle.vue';
import SectionTitle from '@/components/Ui/SectionTitle.vue';
import InputField from '@/components/Ui/InputField.vue';
import PrimaryButton from '@/components/Ui/PrimaryButton.vue';
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
    <div class="w-full relative">
        <svg class="max-w-[1663px] mx-auto" viewBox="0 0 1663 127" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M831.384 0L1662.77 126.809H0L831.384 0Z" fill="#FEF8ED" />
        </svg>

        <div class="bg-sectionBg1 pt-[10px] pb-8">
            <div class="max-w-[1176px] mx-auto px-4 grid grid-cols-1 md:grid-cols-2 gap-4">
                <motion.div 
                    :initial="{ opacity: 0, y: 50 }"
                    :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                    :viewport="{ once: false, amount: 0.3 }"
                    class="w-full space-y-[28px]">
                    <SectionTitle extra-class="text-center md:text-left">
                        Which Payers Cover RTM?
                    </SectionTitle>
                    <SectionSubTitle extra-class="text-center md:text-left">
                        Enter your name, state, and any insurance providers your clinic works with. We’ll look up the info
                        and send you the RTM coverage details!
                    </SectionSubTitle>
    
                    <div class="w-full sm:max-w-[500px] md:max-w-[466px] mx-auto md:mx-0">
                        <img src="/images/rmtFormLeftImg.webp" alt="img" class="w-full">
                    </div>
                </motion.div>
    
                <!-- form area start -->
                <motion.div 
                    :initial="{ opacity: 0, y: 50 }"
                    :inView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
                    :viewport="{ once: false, amount: 0.3 }"
                    class="w-full md:max-w-[374px] flex items-end justify-end mx-auto md:mx-0 md:ml-auto py-[10px]">
                    <form @submit.prevent="handleSubmit" class="w-full space-y-4">
                        <InputField v-model="form.firstName" label="First Name" name="firstName"
                            :error="errors.firstName" />
    
                        <InputField v-model="form.lastName" label="Last Name" name="lastName" :error="errors.lastName" />
    
                        <InputField v-model="form.email" label="Work Email" name="email" type="email"
                            :error="errors.email" />
    
                        <InputField v-model="form.practiceName" label="Practice Name" name="practiceName"
                            :error="errors.practiceName" />
    
                        <InputField v-model="form.state" label="State" name="state" :error="errors.state" />
    
                        <InputField v-model="form.payors" label="Major Payors Your State Accepts" name="payors"
                            :error="errors.payors" />
                        <PrimaryButton primary-type="button" @click="handleSubmit" text="Submit" extra-class="min-w-[140px]" />
                    </form>
                </motion.div>
    
            </div>
        </div>
    </div>
</template>