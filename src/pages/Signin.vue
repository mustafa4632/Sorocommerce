<template>
  <div class="min-h-screen">
    <div class="grid lg:grid-cols-2 sm:gap-10 md:py-8 px-4 md:px-10">
      <div class="">
        <img :src="Logo" alt="" />
        <div class="flex flex-col items-center lg:items-end justify-center mt-12">
          <div class="max-w-[470px] flex flex-col items-center justify-center w-full">
            <div class="flex flex-col items-center gap-3">
              <span class="text-3xl lg:text-5xl	font-bold">Login</span>
              <span class="font-semibold text-base">Or <router-link to="Signup"
                  class="text-primary">Register</router-link> if you don't have an
                Account</span>
            </div>
            <form class="space-y-5 md:space-y-7 mt-10 w-full" action="">
              <div class="relative">
                <label for="email"
                  class="absolute -top-2 left-2 inline-block bg-white px-1 text-xs font-medium text-gray-900">Email</label>
                <input type="text" name="email" id="email"
                  class="bg-white block w-full rounded-md border-0 px-3 py-2.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-inset focus:ring-primary-600 sm:text-sm sm:leading-6"
                  placeholder="Jane@gmail.com" />
                <div class="absolute top-2 right-2 text-gray-400">
                  <EnvelopeIcon class="w-6 h-6" />
                </div>
              </div>
              <div class="relative">
                <label for="password"
                  class="absolute -top-2 left-2 inline-block bg-white px-1 text-xs font-medium text-gray-900">Password</label>
                <input :type="showPassword ? 'text' : 'password'" name="password" id="password"
                  class="bg-white block w-full rounded-md border-0 px-3 py-2.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-inset focus:ring-primary-600 sm:text-sm sm:leading-6"
                  placeholder="Enter your password" />

                <!-- Eye Icon Button -->
                <button type="button" class="absolute top-2 right-2 text-gray-400" @click="togglePassword">
                  <EyeIcon v-if="!showPassword" class="w-6 h-6" />
                  <EyeSlashIcon v-else class="w-6 h-6" />
                </button>
              </div>

              <div class="flex items-center justify-between w-full">
                <div class="relative flex items-start">
                  <div class="flex h-6 items-center">
                    <input id="comments" aria-describedby="comments-description" name="comments" type="checkbox"
                      class="h-4 w-4 rounded border-gray-300 text-primary focus:ring-primary">
                  </div>
                  <div class="ml-3 text-sm leading-6">
                    <label for="comments" class="font-medium text-gray-900 text-sm">Remember me </label>
                  </div>
                </div>
                <div class="">
                  <a class="font-medium text-gray-900 text-sm" href="">Forget password</a>
                </div>
              </div>
              <div class="">
                <button
                  class="text-white font-semibold text-base bg-gradient-to-r from-secondaryblue to-secondarypink py-3.5 w-full rounded-md">Login</button>
              </div>
            </form>
          </div>
        </div>

      </div>
      <div class="hidden lg:flex justify-end h-[700px]">
        <img class="rounded-3xl" :src="loginBanner" alt="" />
      </div>
    </div>
  </div>
</template>

<script setup>
import Logo from "../assets/Logo.png";
import loginBanner from "../assets/loginbanner.png";
import { ref } from 'vue';
import { EyeIcon, EyeSlashIcon } from '@heroicons/vue/24/outline';
import { EnvelopeIcon } from '@heroicons/vue/24/outline'

const showPassword = ref(false);
function togglePassword() {
  showPassword.value = !showPassword.value;
}
</script>