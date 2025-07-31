<script setup lang="ts">
import Header from "./components/Header.vue";
import Footer from "./components/Footer.vue";
import Content from "./components/Content.vue";
</script>

<template>
    <div
        class="h-full min-h-screen w-screen flex flex-col justify-start items-center"
    >
        <Header class="" />
        <Content
            class="flex-1 w-full h-full justify-center items-center flex"
        />
        <Footer class="bg-[#A2D5C6] w-full h-14 lg:h-40" />
    </div>
</template>

<style scoped></style>
