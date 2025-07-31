<script setup lang="ts">
import { onMounted, onUnmounted, ref } from "vue";
import Navbar from "./navbar.vue";

const props = defineProps<{
    class?: string;
}>();
const isAtTop = ref(true);
const isNavOpen = ref(false);
const logo = new URL("../assets/images/tooth.svg", import.meta.url).href;
const title = "Welcome";

const toggleNav = () => {
    isNavOpen.value = !isNavOpen.value;
    const nav = document.querySelector("nav");
    if (nav) {
        nav.classList.toggle("hidden", !isNavOpen.value);
        nav.classList.toggle("flex", isNavOpen.value);
    }
};

const handleNavigate = (section: string) => {
    isNavOpen.value = false;
    const el = document.getElementById(section);
    if (el) {
        el.scrollIntoView({ behavior: "smooth" });
    }
};

const onScroll = () => {
    isAtTop.value = window.scrollY <= 5;
};

onMounted(() => {
    window.addEventListener("scroll", onScroll);
    onScroll();
});

onUnmounted(() => {
    window.removeEventListener("scroll", onScroll);
});
</script>

<template>
    <header
        :class="[
            props.class,
            'bg-[#A2D5C6] w-full h-20 flex items-center justify-between fixed top-0 z-20 transition-all duration-500 px-4',
            { 'bg-[#A2D5C6]/60': !isAtTop },
        ]"
    >
        <img :src="logo" alt="Logo" class="h-16 w-16 mr-4" />
        <h1 class="text-black/50 font-bold md:text-2xl">{{ title }}</h1>

        <nav class="space-x-4 hidden md:flex pr-4" v-if="!isNavOpen">
            <h1
                @click="handleNavigate('home')"
                class="relative text-black/50 after:content-[''] after:absolute after:left-0 after:-bottom-1 after:w-0 after:h-0.5 after:bg-black/50 after:transition-all after:duration-500 hover:after:w-full cursor-pointer"
            >
                Home
            </h1>
            <h1
                @click="handleNavigate('about')"
                class="relative text-black/50 after:content-[''] after:absolute after:left-0 after:-bottom-1 after:w-0 after:h-0.5 after:bg-black/50 after:transition-all after:duration-500 hover:after:w-full cursor-pointer"
            >
                About
            </h1>
            <h1
                @click="handleNavigate('contact')"
                class="relative text-black/50 after:content-[''] after:absolute after:left-0 after:-bottom-1 after:w-0 after:h-0.5 after:bg-black/50 after:transition-all after:duration-500 hover:after:w-full cursor-pointer"
            >
                Contact
            </h1>
        </nav>
        <img
            src="../assets/icons/threebars.svg"
            alt="Menu Icon"
            class="h-8 w-8 md:hidden pr-2 cursor-pointer"
            @click="toggleNav"
        />
        <div
            v-if="isNavOpen"
            class="fixed inset-0 z-40 bg-white/30 backdrop-blur-sm transition-all duration-500"
        ></div>
        <div
            v-if="isNavOpen"
            class="fixed top-0 left-0 z-50 h-screen w-10/12 bg-green-200 transition-all duration-500"
        >
            <Navbar @close="toggleNav" @navigate="handleNavigate" class="" />
        </div>
    </header>
</template>

<style></style>
