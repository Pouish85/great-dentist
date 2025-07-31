<script setup lang="ts">
import { GoogleMap, Marker } from "vue3-google-map";
import { onMounted } from "vue";

const props = defineProps<{
    class?: string;
}>();

const center = { lat: 40.689247, lng: -74.044502 };

const googleMapsAPIKey = import.meta.env.VITE_GOOGLE_MAPS_API_KEY;
onMounted(() => {
    if (!googleMapsAPIKey) {
        console.error("Google Maps API key is not set.");
    }
});
</script>

<template>
    <section
        :class="[
            props.class,
            'flex flex-col min-h-screen w-full pb-14 pt-24 xl:justify-center xl:items-center',
        ]"
    >
        <div
            class="md:w-full md:h-full xl:w-9/12 flex justify-start flex-col md:flex-row items-center md:justify-center md:gap-6 lg:gap-10 xl:py-4 xl:justify-around"
        >
            <div
                class="relative md:h-92 md:w-1/2 flex flex-col items-center justify-center"
            >
                <div class="flex flex-col items-center justify-center xl:gap-4">
                    <h1 class="text-lg xl:text-2xl text-green-800 font-bold">
                        Welcome
                    </h1>
                    <h1 class="text-md text-green-950">to</h1>
                    <h1
                        class="text-3xl xl:text-4xl font-bold text-green-800 text-shadow-2xs text-shadow-green-300"
                    >
                        John Doe's Dental Clinic
                    </h1>
                    <img
                        src="../assets/images/tooth.svg"
                        alt="Tooth icon"
                        class="hidden md:flex absolute top-0 left-0 opacity-20 w-full h-full"
                    />
                </div>
            </div>
            <img
                src="../assets/images/dental-clinic.jpg"
                alt="Clinic photo"
                class="h-auto w-9/12 md:w-1/3 object-cover my-8 rounded-lg xl:h-[400px] xl:w-[500px] xl:object-cover"
            />
        </div>
        <div class="flex justify-center w-full md:mt-5 md:mb-5 xl:py-4">
            <p class="text-green-800 text-md w-9/12 text-center">
                We are dedicated to providing the best dental care for you and
                your family. Our team of experienced professionals is here to
                ensure your smile stays healthy and bright.
            </p>
        </div>
        <div class="hidden md:flex w-full gap-4 justify-center mt-4 xl:py-4">
            <img
                src="../assets/images/jaw.jpg"
                alt="Jaw image"
                class="h-auto w-1/4 object-cover rounded-lg"
            />
            <img
                src="../assets/images/smile.jpg"
                alt="Smile image"
                class="h-auto w-1/4 object-cover rounded-lg md:object-top-right"
            />
            <GoogleMap
                :api-key="googleMapsAPIKey"
                :center="center"
                :zoom="15"
                class="h-auto w-1/4 object-cover rounded-lg"
            >
                <Marker :options="{ position: center }" />
            </GoogleMap>
        </div>
    </section>
</template>

<style></style>
