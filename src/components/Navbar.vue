<script setup lang="ts">
import { ref } from 'vue';
import { RouterLink } from 'vue-router';
import NavLink from './Ui/NavLink.vue';
import PrimaryButton from './Ui/PrimaryButton.vue';
import SecondaryButton from './Ui/SecondaryButton.vue';

const showSidebar = ref(false);

const showAlert = () => {
    alert("clicking from props")
}


</script>

<template>
    <div class="max-w-[1650px] px-4 mx-auto w-full">
        <nav class="flex justify-between gap-2 xl:gap-4">

            <!-- logo start -->
            <RouterLink to="/"
                class="max-w-[130px] md:max-w-[183px] w-full bg-white px-[14px] py-2 xl:py-4 rounded-[8px] xl:rounded-2xl inline-flex items-center justify-center">
                <img src="/logos/phyxcp-health.webp" alt="logo" class="w-full mt-1">
            </RouterLink>
            <!-- logo end -->

            <div class="bg-white px-6 rounded-[8px] xl:rounded-2xl flex-1
                hidden xl:flex items-center py-1 gap-2 2xl:gap-4 justify-between">
                <div class="flex items-center gap-5 2xl:gap-8">
                    <NavLink text="Home" url="/" />
                    <NavLink text="Products" url="/products" />
                    <NavLink text="Solutions" url="/solutions" />
                    <NavLink text="Blog" url="/blog" />
                    <NavLink text="pricing" url="/Pricing" />
                    <NavLink text="About Us" url="/about-us" />
                </div>

                <div class="flex gap-2 2xl:gap-4">
                    <PrimaryButton primaryType="link" to="/request-demo" text="Request Demo" extra-class="min-w-[172px]" />
                    <SecondaryButton secondaryType="button" text="Free Trial" @click="showAlert" extra-class="min-w-[172px]" />
                </div>
            </div>

            <div class="flex gap-2">
                <!-- login button -->
                <div class="bg-white shrink-0 rounded-[8px] xl:rounded-2xl px-[22px] flex items-center justify-center">
                    <NavLink text="Log In" url="/login" />
                </div>

                <div class="flex items-center xl:hidden">
                    <SecondaryButton secondary-type="button" @click="showSidebar = !showSidebar">
                        <svg class="w-[20px]" viewBox="0 0 12 10" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path fill-rule="evenodd" clip-rule="evenodd"
                                d="M0 9.5C0 9.22386 0.223858 9 0.5 9H7.5C7.77614 9 8 9.22386 8 9.5C8 9.77614 7.77614 10 7.5 10H0.5C0.223858 10 0 9.77614 0 9.5Z"
                                fill="black" />
                            <path fill-rule="evenodd" clip-rule="evenodd"
                                d="M0 6.5C0 6.22386 0.223858 6 0.5 6H11.5C11.7761 6 12 6.22386 12 6.5C12 6.77614 11.7761 7 11.5 7H0.5C0.223858 7 0 6.77614 0 6.5Z"
                                fill="black" />
                            <path fill-rule="evenodd" clip-rule="evenodd"
                                d="M0 3.5C0 3.22386 0.223858 3 0.5 3H11.5C11.7761 3 12 3.22386 12 3.5C12 3.77614 11.7761 4 11.5 4H0.5C0.223858 4 0 3.77614 0 3.5Z"
                                fill="black" />
                            <path fill-rule="evenodd" clip-rule="evenodd"
                                d="M0 0.5C0 0.223858 0.223858 0 0.5 0H11.5C11.7761 0 12 0.223858 12 0.5C12 0.776142 11.7761 1 11.5 1H0.5C0.223858 1 0 0.776142 0 0.5Z"
                                fill="black" />
                        </svg>
                    </SecondaryButton>
                </div>
            </div>

        </nav>

        <!-- overlay start -->
         <div @click="showSidebar = !showSidebar" 
            :class="[showSidebar ? 'opacity-100 visible pointer-events-auto' : 'opacity-0 invisible pointer-events-none']"
            class="fixed inset-0 bg-black/10 z-30 backdrop-blur transition-all duration-300"></div>
        <!-- overlay end -->
        <div
            :class="[showSidebar ? 'translate-x-0' : 'translate-x-full']"
          class="fixed z-50 top-0 right-0 h-screen max-w-[380px] w-full transition-all duration-300">
            <div class="bg-white h-full rounded-[8px] overflow-y-auto relative border border-bdr">
                <div class="bg-white text-end p-2 sticky top-0 left-0">
                    <SecondaryButton secondary-type="button" @click="showSidebar = !showSidebar">
                        <svg class="w-[20px]" viewBox="0 0 12 12" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path
                                d="M0.146447 0.853554C-0.0488156 0.658291 -0.0488156 0.341709 0.146447 0.146447C0.341709 -0.0488155 0.658292 -0.0488155 0.853554 0.146447L6 5.29289L11.1464 0.146447C11.3417 -0.0488155 11.6583 -0.0488155 11.8536 0.146447C12.0488 0.341709 12.0488 0.658291 11.8536 0.853554L6.70711 6L11.8536 11.1464C12.0488 11.3417 12.0488 11.6583 11.8536 11.8536C11.6583 12.0488 11.3417 12.0488 11.1464 11.8536L6 6.70711L0.853554 11.8536C0.658292 12.0488 0.341709 12.0488 0.146447 11.8536C-0.048815 11.6583 -0.048815 11.3417 0.146447 11.1464L5.29289 6L0.146447 0.853554Z"
                                fill="black" />
                        </svg>
                    </SecondaryButton>
                </div>
                <div class="px-4 space-y-4">
                    <div class="flex flex-col items-start gap-2">
                        <NavLink text="Home" url="/" />
                        <NavLink text="Products" url="/products" />
                        <NavLink text="Solutions" url="/solutions" />
                        <NavLink text="Blog" url="/blog" />
                        <NavLink text="pricing" url="/Pricing" />
                        <NavLink text="About Us" url="/about-us" />
                    </div>

                    <div class="flex gap-2">
                        <PrimaryButton primaryType="link" to="/" text="Request Demo" extra-class="w-1/2" />
                        <SecondaryButton secondary-type="button" text="Free Trial" @click="showAlert" extra-class="w-1/2" />
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>