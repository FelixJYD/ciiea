<script setup>
import HomeNavbar from "@/Components/Partials/HomeNavbar.vue";
import HomeFooter from "@/Components/Partials/HomeFooter.vue";

const props = defineProps({
    canLogin: {
        type: Boolean,
    },
    canRegister: {
        type: Boolean,
    },
});
</script>

<template>
    <div class="min-h-screen w-full bg-neutral-200">
        <!-- Navbar -->
        <HomeNavbar :canLogin="canLogin" :canRegister="canRegister" />

        <!-- Page Content -->
        <main class="min-h-screen sm:pt-14">
            <slot />
        </main>

        <!-- Footer -->
        <HomeFooter />
    </div>
</template>
