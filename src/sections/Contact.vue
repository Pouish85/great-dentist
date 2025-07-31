<script setup lang="ts">
const props = defineProps<{
    class?: string;
}>();
</script>

<template>
    <section
        :class="[
            props.class,
            'min-h-screen w-full flex justify-start pb-4 flex-col items-center pt-24 lg:justify-center',
        ]"
    >
        <div class="flex flex-col items-center w-full">
            <h1
                class="text-3xl font-bold text-green-800 text-shadow-2xs text-shadow-green-300"
            >
                Contact us
            </h1>
            <p class="text-green-800 text-md w-9/12 text-center my-4">
                For inquiries, appointments, or feedback, please reach out to us
                through the following channels:
            </p>
        </div>
        <div class="flex gap-4 items-center my-4">
            <a href="#" target="_blank"
                ><img
                    src="../assets/icons/instagram.svg"
                    alt="Instagram icon"
                    title="Contact us on Instagram"
                    class="h-8 w-8"
            /></a>
            <a href="#" target="_blank"
                ><img
                    src="../assets/icons/LinkedIn.svg"
                    alt="LinkedIn icon"
                    title="Contact us on LinkedIn"
                    class="h-11 w-11"
            /></a>
        </div>
        <div class="flex flex-col lg:flex-row items-center w-full lg:w-10/12">
            <div class="flex flex-col gap-2 justify-center mb-5">
                <div class="flex items-center">
                    <img
                        src="../assets/icons/phone.svg"
                        alt="Phone icon"
                        class="h-6 w-6"
                    />
                    <span class="text-green-800 text-md ml-2"
                        >+1 (123) 456-7890</span
                    >
                </div>
                <div class="flex items-center">
                    <img
                        src="../assets/icons/email.svg"
                        alt="Email icon"
                        class="h-6 w-6"
                    />
                    <span class="text-green-800 text-md ml-2"
                        >johnsDoesClinic@Dental-office.com</span
                    >
                </div>
                <div class="flex items-center">
                    <img
                        src="../assets/icons/location.svg"
                        alt="Location icon"
                        class="h-6 w-6"
                    />
                    <span class="text-green-800 text-md ml-2"
                        >123 Dental St, Tooth City, TC 12345</span
                    >
                </div>
                <div class="flex items-center">
                    <img
                        src="../assets/icons/time.svg"
                        alt="Office Hour icon"
                        class="h-6 w-6"
                    />
                    <div class="text-green-800 text-sm ml-2">
                        <p>Monday: 8am - 6pm</p>
                        <p>Tuesday: 8am - 6pm</p>
                        <p>Wednesday: 8am - 6pm</p>
                        <p>Thursday: 8am - 6pm</p>
                        <p>Friday: 8am - 5pm</p>
                        <p>Saturday: 9am - 2pm</p>
                    </div>
                </div>
            </div>
            <div class="flex flex-col items-center">
                <p class="text-green-800 text-md w-9/12 text-center my-5">
                    If you want to contact us directly, please fill out the form
                    below and we will get back to you as soon as possible.
                </p>
                <form class="w-9/12 flex flex-col gap-4">
                    <input
                        type="text"
                        placeholder="Your Name"
                        class="p-2 border border-green-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-green-500"
                    />
                    <input
                        type="email"
                        placeholder="Your Email"
                        class="p-2 border border-green-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-green-500"
                    />
                    <textarea
                        placeholder="Your Message"
                        class="p-2 border border-green-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-green-500 h-32"
                    ></textarea>
                    <button
                        type="submit"
                        class="bg-[#A2D5C6] text-white p-2 rounded-lg hover:bg-green-700 transition duration-300"
                    >
                        Send Message
                    </button>
                </form>
            </div>
        </div>
    </section>
</template>

<style scoped></style>
