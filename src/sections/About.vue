<script setup lang="ts">
import { ref } from "vue";

const props = defineProps<{
    class?: string;
}>();
const textToShow = ref("");

const handleClick = (name: string) => {
    if (textToShow.value === name) {
        textToShow.value = "";
    } else {
        textToShow.value = name;
    }
};
</script>

<template>
    <section
        :class="[
            props.class,
            'min-h-screen w-full flex justify-start pb-14 flex-col items-center pt-24',
        ]"
    >
        <h1
            class="text-3xl font-bold text-green-300 text-shadow-2xs text-shadow-green-800"
        >
            Our special team
        </h1>
        <h1 class="text-lg text-green-800 font-bold my-4">
            Meet our dedicated professionals
        </h1>
        <h1 class="text-2xl text-green-950">Our dentists</h1>
        <div
            class="flex flex-col items-center md:flex-row md:justify-around md:w-full"
        >
            <div class="flex flex-col items-center">
                <h1 class="text-xl text-green-800 font-bold my-2">Karen</h1>
                <div
                    class="relative flex justify-center group mb-4"
                    @click="handleClick('karen')"
                >
                    <div
                        class="w-9/12 md:w-auto md:object-cover flex justify-center items-center relative"
                    >
                        <img
                            src="../assets/images/karen.jpg"
                            alt="Karen picture"
                            class="w-full rounded-2xl md:h-[450px] md:max-w-[300px] lg:w-[450px] lg:max-w-full lg:h-[400px] object-cover lg:object-top"
                        />
                        <img
                            src="../assets/icons/touch.svg"
                            alt="Touch icon"
                            class="absolute top-2 right-2 w-auto h-6 md:h-8"
                        />
                    </div>
                    <p
                        :class="[
                            textToShow === 'karen'
                                ? 'opacity-100 pointer-events-auto'
                                : 'opacity-0 pointer-events-none',
                            'group-hover:opacity-100 group-hover:pointer-events-auto w-9/12 md:w-auto absolute bottom-0 bg-green-300/80 text-green-800 text-center p-2 rounded-b-2xl z-10 transition-all duration-300 md:duration-500',
                        ]"
                    >
                        Karen is a highly skilled dentist with over 10 years of
                        experience in the field. She specializes in cosmetic
                        dentistry and is passionate about creating beautiful
                        smiles.
                    </p>
                </div>
            </div>
            <div class="flex flex-col items-center">
                <h1 class="text-xl text-green-800 font-bold my-2">John</h1>
                <div
                    class="relative flex justify-center group mb-4"
                    @click="handleClick('john')"
                >
                    <div
                        class="w-9/12 md:w-auto md:object-contain flex justify-center items-center relative"
                    >
                        <img
                            src="../assets/images/john.jpg"
                            alt="John's picture"
                            class="w-full rounded-2xl md:h-[450px] md:max-w-[300px] lg:w-[450px] lg:max-w-full lg:h-[400px] object-cover lg:object-top"
                        />
                        <img
                            src="../assets/icons/touch.svg"
                            alt="Touch icon"
                            class="absolute top-2 right-2 w-auto h-6 md:h-8"
                        />
                    </div>
                    <p
                        :class="[
                            textToShow === 'john'
                                ? 'opacity-100 pointer-events-auto'
                                : 'opacity-0 pointer-events-none',
                            'group-hover:opacity-100 group-hover:pointer-events-auto w-9/12 md:w-auto absolute bottom-0 bg-green-300/80 text-green-800 text-center p-2 rounded-b-2xl z-10 transition-all duration-300 md:duration-500',
                        ]"
                    >
                        John is a dedicated dentist with a focus on family
                        dentistry. He believes in providing gentle care and
                        building long-term relationships with his patients.
                    </p>
                </div>
            </div>
        </div>
        <h1 class="text-2xl text-green-950">Our nurses</h1>
        <div
            class="flex flex-col items-center md:flex-row md:justify-around md:w-full"
        >
            <div class="flex flex-col items-center">
                <h1 class="text-xl text-green-800 font-bold my-2">Suzan</h1>
                <div
                    class="relative flex justify-center group mb-4"
                    @click="handleClick('suzan')"
                >
                    <div
                        class="w-9/12 md:w-auto md:object-cover flex justify-center items-center relative"
                    >
                        <img
                            src="../assets/images/suzan.jpg"
                            alt="Suzan picture"
                            class="w-full rounded-2xl md:h-[450px] md:max-w-[300px] lg:w-[450px] lg:max-w-full lg:h-[400px] object-cover lg:object-top"
                        />
                        <img
                            src="../assets/icons/touch.svg"
                            alt="Touch icon"
                            class="absolute top-2 right-2 w-auto h-6 md:h-8"
                        />
                    </div>
                    <p
                        :class="[
                            textToShow === 'suzan'
                                ? 'opacity-100 pointer-events-auto'
                                : 'opacity-0 pointer-events-none',
                            'group-hover:opacity-100 group-hover:pointer-events-auto w-9/12 md:w-auto absolute bottom-0 bg-green-300/80 text-green-800 text-center p-2 rounded-b-2xl z-10 transition-all duration-300 md:duration-500',
                        ]"
                    >
                        Suzan is a compassionate dental nurse with a keen eye
                        for detail. She ensures that every patient feels
                        comfortable and well-cared for during their visit.
                    </p>
                </div>
            </div>
            <div class="flex flex-col items-center">
                <h1 class="text-xl text-green-800 font-bold my-2">Roberto</h1>
                <div
                    class="relative flex justify-center group mb-4"
                    @click="handleClick('roberto')"
                >
                    <div
                        class="w-9/12 md:w-auto md:object-contain flex justify-center items-center relative"
                    >
                        <img
                            src="../assets/images/roberto.jpg"
                            alt="Roberto picture"
                            class="w-full rounded-2xl md:h-[450px] md:max-w-[300px] lg:w-[450px] lg:max-w-full lg:h-[400px] object-cover lg:object-top"
                        />
                        <img
                            src="../assets/icons/touch.svg"
                            alt="Touch icon"
                            class="absolute top-2 right-2 w-auto h-6 md:h-8"
                        />
                    </div>
                    <p
                        :class="[
                            textToShow === 'roberto'
                                ? 'opacity-100 pointer-events-auto'
                                : 'opacity-0 pointer-events-none',
                            'group-hover:opacity-100 group-hover:pointer-events-auto w-9/12 md:w-auto absolute bottom-0 bg-green-300/80 text-green-800 text-center p-2 rounded-b-2xl z-10 transition-all duration-300 md:duration-500',
                        ]"
                    >
                        Roberto is a skilled dental nurse who is always ready to
                        assist our dentists. His friendly demeanor and expertise
                        make him a valuable member of our team.
                    </p>
                </div>
            </div>
        </div>
        <h1 class="text-2xl text-green-950">Our secretary</h1>
        <div
            class="flex flex-col items-center md:flex-row md:justify-around md:w-full"
        >
            <div class="flex flex-col items-center">
                <h1 class="text-xl text-green-800 font-bold my-2">Monica</h1>
                <div
                    class="relative flex justify-center group mb-4"
                    @click="handleClick('monica')"
                >
                    <div
                        class="w-9/12 md:w-auto md:object-cover flex justify-center items-center relative"
                    >
                        <img
                            src="../assets/images/monica.jpg"
                            alt="Monica picture"
                            class="w-full rounded-2xl md:h-[450px] md:max-w-[300px] lg:w-[450px] lg:max-w-full lg:h-[400px] object-cover"
                        />
                        <img
                            src="../assets/icons/touch.svg"
                            alt="Touch icon"
                            class="absolute top-2 right-2 w-auto h-6 md:h-8"
                        />
                    </div>
                    <p
                        :class="[
                            textToShow === 'monica'
                                ? 'opacity-100 pointer-events-auto'
                                : 'opacity-0 pointer-events-none',
                            'group-hover:opacity-100 group-hover:pointer-events-auto w-9/12 md:w-auto absolute bottom-0 bg-green-300/80 text-green-800 text-center p-2 rounded-b-2xl z-10 transition-all duration-300 md:duration-500',
                        ]"
                    >
                        Monica is the friendly face of our clinic. She manages
                        appointments and ensures that everything runs smoothly
                        behind the scenes. Her organizational skills are
                        unmatched.
                    </p>
                </div>
            </div>
        </div>
    </section>
</template>

<style></style>
