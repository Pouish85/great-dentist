<script setup lang="ts">
import Modal from "./Modal.vue";
import { ref } from "vue";
import TermsModal from "./TermsModal.vue";
import CertifModal from "./CertifModal.vue";

const props = defineProps<{
    class?: string;
}>();
const isModalOpen = ref(false);

const toggleModal = () => {
    isModalOpen.value = !isModalOpen.value;
    console.log(`Modal is now ${isModalOpen.value ? "open" : "closed"}`);
};

const footerText = "John Doe's Dental Clinic © 2025. All rights reserved.";
</script>

<template>
    <footer
        :class="[
            props.class,
            'flex items-center justify-center lg:flex-col lg:justify-around gap-4',
        ]"
    >
        <div
            class="hidden lg:flex items-center justify-center w-full gap-4 text-black/50 font-bold"
        >
            <div
                v-if="isModalOpen"
                class="fixed inset-0 z-40 bg-white/30 backdrop-blur-sm transition-all duration-500"
            ></div>
            <div
                class="relative text-black/50 after:content-[''] after:absolute after:left-0 after:-bottom-1 after:w-0 after:h-0.5 after:bg-black/50 after:transition-all after:duration-500 hover:after:w-full cursor-pointer outer"
            >
                <div @click="toggleModal">
                    <TermsModal />
                </div>
            </div>
            <h1
                class="relative text-black/50 after:content-[''] after:absolute after:left-0 after:-bottom-1 after:w-0 after:h-0.5 after:bg-black/50 after:transition-all after:duration-500 hover:after:w-full cursor-pointer"
            >
                <CertifModal />
            </h1>
            <div class="flex flex-col">
                <h1 class="text-black/50">Accepted Payment Methods</h1>
                <div class="flex gap-2 items-center justify-center mt-2">
                    <img
                        src="../assets/icons/visa.svg"
                        alt="Visa"
                        class="h-7 w-auto"
                    />
                    <img
                        src="../assets/icons/mastercard.svg"
                        alt="MasterCard"
                        class="h-7 w-auto"
                    />
                    <img
                        src="../assets/icons/paypal.svg"
                        alt="PayPal"
                        class="h-7 w-auto"
                    />
                </div>
            </div>
            <div class="flex flex-col">
                <h1 class="text-black/50">Newsletter</h1>
                <div class="w-full flex justify-center items-center">
                    <input
                        type="email"
                        placeholder="Enter your email"
                        class="p-2 rounded-md border border-black/50 text-black/50 focus:outline-none focus:ring-2 focus:ring-black/50 w-64"
                    />
                    <button
                        class="ml-2 bg-black/50 text-white px-4 py-2 rounded-md hover:bg-green-600 transition-colors"
                    >
                        Subscribe
                    </button>
                </div>
            </div>
        </div>
        <h1 class="text-black/50 font-bold text-sm">{{ footerText }}</h1>
    </footer>
</template>

<style scoped></style>
