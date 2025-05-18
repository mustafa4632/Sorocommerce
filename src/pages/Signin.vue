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
                <button @click="showModal = true"
                  class="text-white font-semibold text-base bg-gradient-to-r from-secondaryblue to-secondarypink py-3.5 w-full rounded-md">
                  Login
                </button>
              </div>
            </form>

          </div>
        </div>
        <button @click="showModal = true"
          class="text-white font-semibold text-base bg-gradient-to-r from-secondaryblue to-secondarypink py-3.5 w-[100px] mt-12 rounded-md">
          Fire Modal
        </button>
      </div>
      <div class="hidden lg:flex justify-end h-[700px]">
        <img class="rounded-3xl" :src="loginBanner" alt="" />
      </div>
    </div>
  </div>

  <!-- Modal -->
  <transition name="fade">
    <div v-if="showModal" class="fixed inset-0 z-50 flex items-center justify-center bg-black bg-opacity-50">
      <div class="bg-white rounded-lg shadow-xl w-[30rem] p-4 relative">
        <!-- Header -->
        <div class="flex justify-between items-center mb-4">
          <h2 class="text-lg font-semibold">Select Network</h2>
          <button @click="showModal = false" class="text-gray-500 hover:text-black w-6 h-6">
            <XMarkIcon class="w-6 h-6" />
          </button>
        </div>

        <!-- Network List -->
        <div class="space-y-2">
          <div class="flex items-center justify-between p-2 rounded hover:bg-gray-100 transition border-b-2 pb-3">
            <div class="flex items-center space-x-3">
              <img :src="Steller" alt="" class="w-10 h-10 rounded-full" />
              <span class="text-sm font-medium text-gray-800">Steller</span>
            </div>
            <div>
              <ChevronRightIcon class="w-4 h-4 text-gray-400" />
            </div>
          </div>
          <div class="flex items-center justify-between p-2 rounded hover:bg-gray-100 transition border-b-2 pb-3">
            <div class="flex items-center space-x-3">
              <img :src="Ripple" alt="" class="w-10 h-10 rounded-full" />
              <span class="text-sm font-medium text-gray-800">Ripple</span>
            </div>
            <div>
              <ChevronRightIcon class="w-4 h-4 text-gray-400" />
            </div>
          </div>
          <div class="flex items-center justify-between p-2 rounded hover:bg-gray-100 transition border-b-2 pb-3">
            <div class="flex items-center space-x-3">
              <img :src="Hedera" alt="" class="w-10 h-10 rounded-full" />
              <span class="text-sm font-medium text-gray-800">Hedera</span>
            </div>
            <div class="text-xs bg-gray-200 text-gray-500 px-2 py-0.5 rounded-full">
              Coming soon
            </div>
          </div>
          <div class="flex items-center justify-between p-2 rounded hover:bg-gray-100 transition border-b-2 pb-3">
            <div class="flex items-center space-x-3">
              <img :src="Aptos" alt="" class="w-10 h-10 rounded-full" />
              <span class="text-sm font-medium text-gray-800">Aptos</span>
            </div>
            <div class="text-xs bg-gray-200 text-gray-500 px-2 py-0.5 rounded-full">
              Coming soon
            </div>
          </div>
          <div class="flex items-center justify-between p-2 rounded hover:bg-gray-100 transition border-b-2 pb-3">
            <div class="flex items-center space-x-3">
              <img :src="Vechain" alt="" class="w-10 h-10 rounded-full" />
              <span class="text-sm font-medium text-gray-800">VeChain</span>
            </div>
            <div class="text-xs bg-gray-200 text-gray-500 px-2 py-0.5 rounded-full">
              Coming soon
            </div>
          </div>
          <div class="flex items-center justify-between p-2 rounded hover:bg-gray-100 transition border-b-2 pb-3">
            <div class="flex items-center space-x-3">
              <img :src="Algorand" alt="" class="w-10 h-10 rounded-full" />
              <span class="text-sm font-medium text-gray-800">Algorand</span>
            </div>
            <div class="text-xs bg-gray-200 text-gray-500 px-2 py-0.5 rounded-full">
              Coming soon
            </div>
          </div>
          <div class="flex items-center justify-between p-2 rounded hover:bg-gray-100 transition border-b-2 pb-3">
            <div class="flex items-center space-x-3">
              <img :src="Celo" alt="" class="w-10 h-10 rounded-full" />
              <span class="text-sm font-medium text-gray-800">Celo</span>
            </div>
            <div class="text-xs bg-gray-200 text-gray-500 px-2 py-0.5 rounded-full">
              Coming soon
            </div>
          </div>
        </div>
      </div>
    </div>
  </transition>

</template>
<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>

<script setup>
import Logo from "../assets/Logo.png";
import loginBanner from "../assets/loginbanner.png";
import Steller from "../assets/stellar.png";
import Ripple from "../assets/ripple.png";
import Hedera from "../assets/hedera.png";
import Aptos from "../assets/aptos.png";
import Vechain from "../assets/vechain.jpg";
import Algorand from "../assets/algorand.png";
import Celo from "../assets/celo.png";
import { ref } from 'vue';
import { EyeIcon, EyeSlashIcon, EnvelopeIcon, XMarkIcon, ChevronRightIcon } from '@heroicons/vue/24/outline';


const showPassword = ref(false);
function togglePassword() {
  showPassword.value = !showPassword.value;
}
const showModal = ref(false)
</script>