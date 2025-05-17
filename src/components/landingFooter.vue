<template>
    <footer class="bg-gradient-to-b from-white to-transparent md:rounded-t-[10rem] mt-5">
        <div class="max-w-7xl mx-auto text-gray-500 px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-10 py-20 text-center md:text-left">
                <!-- Logo + Description -->
                <div class="flex flex-col items-center md:items-start">
                    <img class="w-44 lg:w-auto" :src="Logo" alt="">
                    <p class="text-sm mt-3 pr-0 md:pr-12">
                        Empowering freelancers and businesses with blockchain-driven marketplace solutions.
                    </p>
                </div>

                <!-- Quick Links -->
                <ul class="space-y-2">
                    <p class="text-black font-bold">Quick Links</p>
                    <li><router-link to="/about">About us</router-link></li>
                    <li>Connect with us</li>
                </ul>

                <!-- Useful Links -->
                <ul class="space-y-3">
                    <p class="text-black font-bold">Useful Links</p>
                    <li><router-link to="/contact_us">Contact us</router-link></li>
                    <li><router-link to="/terms&condition">Terms & Conditions</router-link></li>
                    <li><router-link to="/faqs">FAQs</router-link></li>
                </ul>

                <!-- Social Links -->
                <ul class="space-y-2">
                    <p class="text-black font-bold">Follow Us</p>
                    <div class="flex justify-center md:justify-start gap-3">
                        <a href=""><img :src="Link1" alt=""></a>
                        <a href=""><img :src="Link2" alt=""></a>
                        <a href=""><img :src="Link3" alt=""></a>
                    </div>
                </ul>
            </div>

            <!-- Copyright -->
            <div class="border-t py-5 text-center">
                <p class="text-md font-medium text-black">Copyright © 2024, Sorocommerce LLC</p>
            </div>
        </div>
    </footer>
</template>

<script setup>
import Logo from '../assets/Logo.png';
import Link1 from '../assets/Frame 15.png';
import Link2 from '../assets/Frame 16.png';
import Link3 from '../assets/Frame 17.png';
import Link4 from '../assets/Frame 18.png';
import Link5 from '../assets/Frame 19.png';
</script>