<template>
  <div class="min-h-screen">
    <div class="grid lg:grid-cols-2 sm:gap-10 md:py-8 px-4 md:px-10">
      <div class="">
        <img :src="Logo" alt="" />
        <div class="flex flex-col items-center lg:items-end justify-center mt-12 lg:mt-12">
          <div class="max-w-lg flex flex-col items-center justify-center">
            <div class="flex flex-col items-center gap-3">
              <span class="text-3xl lg:text-5xl	font-bold">Register</span>
              <span class="font-semibold text-base">Or <router-link to="SignIn" class="text-primary">Login</router-link>
                if you already have an
                Account</span>
            </div>
            <form class="space-y-5 md:space-y-7 mt-10" action="">
              <!-- Email -->
              <div class="relative">
                <label for="email"
                  class="absolute -top-2 left-2 bg-white px-1 text-xs font-medium text-gray-600">Email</label>
                <input type="text" id="email" name="email"
                  class="bg-white w-full rounded-md border-0 px-3 py-2.5 pr-10 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-primary-600 sm:text-sm"
                  placeholder="Jane@gmail.com" />
                <EnvelopeIcon class="absolute top-2 right-2 w-5 h-5 text-gray-400" />
              </div>

              <!-- Username -->
              <div class="relative">
                <label for="username"
                  class="absolute -top-2 left-2 bg-white px-1 text-xs font-medium text-gray-600">Username</label>
                <input type="text" id="username" name="username"
                  class="bg-white w-full rounded-md border-0 px-3 py-2.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-primary-600 sm:text-sm"
                  placeholder="jane_doe" />
                <UserIcon class="absolute top-2 right-2 w-5 h-5 text-gray-400" />
              </div>

              <!-- Password -->
              <div class="relative">
                <label for="password"
                  class="absolute -top-2 left-2 bg-white px-1 text-xs font-medium text-gray-600">Password</label>
                <input :type="showPassword ? 'text' : 'password'" id="password" name="password"
                  class="bg-white w-full rounded-md border-0 px-3 py-2.5 pr-10 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-primary-600 sm:text-sm"
                  placeholder="••••••••" />
                <button type="button" @click="togglePassword" class="absolute top-2 right-2 text-gray-400">
                  <EyeIcon v-if="!showPassword" class="w-5 h-5" />
                  <EyeSlashIcon v-else class="w-5 h-5" />
                </button>
              </div>

              <!-- Repeat Password -->
              <div class="relative">
                <label for="repeat-password"
                  class="absolute -top-2 left-2 bg-white px-1 text-xs font-medium text-gray-600">Repeat Password</label>
                <input :type="showRepeatPassword ? 'text' : 'password'" id="repeat-password" name="repeat-password"
                  class="bg-white w-full rounded-md border-0 px-3 py-2.5 pr-10 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-primary-600 sm:text-sm"
                  placeholder="••••••••" />
                <button type="button" @click="toggleRepeatPassword" class="absolute top-2 right-2 text-gray-400">
                  <EyeIcon v-if="!showRepeatPassword" class="w-5 h-5" />
                  <EyeSlashIcon v-else class="w-5 h-5" />
                </button>
              </div>

              <!-- Terms -->
              <div class="relative flex items-start">
                <div class="flex h-6 items-center">
                  <input id="terms" name="terms" type="checkbox"
                    class="h-4 w-4 rounded border-gray-300 text-primary focus:ring-primary" />
                </div>
                <div class="ml-3 text-sm leading-6">
                  <label for="terms" class="font-semibold text-gray-900 text-[14px]">
                    By registering, you agree to our
                    <span id="terms-description" class="text-primary font-semibold">
                      <a href="">Terms of Service and Privacy Policy</a>
                    </span>
                  </label>

                </div>
              </div>

              <!-- Submit -->
              <div>
                <button type="submit"
                  class="text-white font-semibold text-base bg-gradient-to-r from-secondaryblue to-secondarypink py-3.5 w-full rounded-md">
                  Create Account
                </button>
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
import { ref } from 'vue'
import { EnvelopeIcon, UserIcon, EyeIcon, EyeSlashIcon } from '@heroicons/vue/24/outline'

const showPassword = ref(false)
const showRepeatPassword = ref(false)

const togglePassword = () => {
  showPassword.value = !showPassword.value
}

const toggleRepeatPassword = () => {
  showRepeatPassword.value = !showRepeatPassword.value
}

</script>
