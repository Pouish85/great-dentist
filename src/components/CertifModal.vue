<script setup lang="ts">
import { ref } from "vue";

const open = ref(false);
</script>

<template>
    <button @click="open = true">Certifications</button>

    <div
        v-if="open"
        class="fixed z-50 top-1/4 left-1/2 w-[50vw] min-h-[50vh] -ml-[25vw] bg-white border border-black/30 rounded-lg flex flex-col items-center"
    >
        <p class="text-black text-2xl mb-4 mt-1">Our Certifications</p>
        <img
            src="../assets/icons/cross.svg"
            @click="open = false"
            class="absolute top-2 right-2 w-6 h-6"
        />
        <ul class="text-gray-700 p-4 list-disc list-inside">
            <li>
                <strong>American Dental Association (ADA) Accreditation</strong>
                — Official certification ensuring compliance with national
                dental care standards.
            </li>
            <li>
                <strong>OSHA Compliance Certificate</strong> — Certificate of
                compliance with Occupational Safety and Health Administration
                safety and hygiene standards.
            </li>
            <li>
                <strong>CPR & Basic Life Support (BLS) Certification</strong> —
                Certified training in cardiopulmonary resuscitation and first
                aid.
            </li>
            <li>
                <strong>State Board Dental License</strong> — Professional
                license issued by the state for the legal practice of dentistry.
            </li>
            <li>
                <strong>HIPAA Compliance Training</strong> — Certification in
                patient medical data protection training.
            </li>
        </ul>
        <p class="text-gray-700 p-4">
            These certifications demonstrate our commitment to quality, safety,
            and patient confidentiality.
        </p>
    </div>
</template>

<style scoped>
.modal {
    position: fixed;
    z-index: 999;
    top: 20%;
    left: 50%;
    width: 300px;
    margin-left: -150px;
}
</style>
