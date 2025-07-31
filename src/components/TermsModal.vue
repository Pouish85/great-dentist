<script setup lang="ts">
import { ref } from "vue";

const open = ref(false);
</script>

<template>
    <button @click="open = true">Terms of Service</button>

    <div
        v-if="open"
        class="fixed z-50 top-1/4 left-1/2 w-[50vw] min-h-[50vh] -ml-[25vw] bg-white border border-black/30 rounded-lg flex flex-col items-center"
    >
        <p class="text-black text-2xl mb-4 mt-1">Terms of Service</p>
        <img
            src="../assets/icons/cross.svg"
            @click="open = false"
            class="absolute top-2 right-2 w-6 h-6"
        />
        <p class="text-gray-700 p-4">
            These are the terms of service for our dental clinic. Please read
            them carefully.
        </p>
        <p class="text-gray-700 p-4 text-justify">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suscipit
            esse eiusmod ullamcorper, wisi odio cum qui officia voluptua
            volutpat exerci nisl nisl volutpat diam congue nisi. Suscipit soluta
            iure.
        </p>
        <p class="text-gray-700 p-4 text-justify">
            Nibh velit, enim aliquam minim iure laboris luptatum eu invidunt
            euismod excepteur justo wisi consetetur non. Vero eros aliquyam
            dolore facer aliquam consectetuer, est dolore luptatum hendrerit
            lorem ipsum doming dolore duis nonumy culpa proident rebum nisl
            possim. No te aliqua. Ipsum laborum magna.
        </p>
        <p class="text-gray-700 p-4 text-justify">
            Soluta hendrerit facer vero elitr deserunt lorem. Iriure quis
            lobortis. Feugiat sit cillum nulla id nisi pariatur sint. Possim
            takimata accusam facilisis doming proident liber mazim placerat
            luptatum. Dolore odio ullamco.
        </p>
        <p class="text-gray-700 p-4">
            By using our services, you agree to these terms.
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
