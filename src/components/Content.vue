<script setup lang="ts">
import Home from "../sections/Home.vue";
import Contact from "../sections/Contact.vue";
import About from "../sections/About.vue";

const props = defineProps<{
    class?: string;
}>();
</script>

<template>
    <main :class="[props.class, 'flex flex-col']">
        <Home class="bg-gray-100 text-black" id="home" />
        <About class="bg-[#B3FFE8]" id="about" />
        <Contact class="bg-gray-100 text-black" id="contact" />
    </main>
</template>

<style scoped></style>
