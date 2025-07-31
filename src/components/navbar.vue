<script setup lang="ts">
const props = defineProps<{
    class?: string;
}>();
const emit = defineEmits(["close", "navigate"]);
</script>

<template>
    <div :class="[props.class, 'relative']">
        <img
            src="../assets/icons/cross.svg"
            alt="close icon"
            class="h-8 w-8 absolute top-2 right-2 cursor-pointer"
            @click="emit('close')"
        />
        <h1
            class="text-yellow-500 font-bold text-xl pt-14 pl-4 cursor-pointer"
            @click="emit('navigate', 'home')"
        >
            Home
        </h1>
        <h1
            class="text-yellow-500 font-bold text-xl pt-14 pl-4 cursor-pointer"
            @click="emit('navigate', 'about')"
        >
            About Us
        </h1>
        <h1
            class="text-yellow-500 font-bold text-xl pt-14 pl-4 cursor-pointer"
            @click="emit('navigate', 'contact')"
        >
            Contact Us
        </h1>
    </div>
</template>

<style scoped></style>
