<template>
  <!-- Full-screen container with vertical split -->
  <div class="flex h-screen w-full">
    <!-- Gradient section with a centered card -->
    <div
      class="hidden lg:flex w-1/2 bg-gradient-to-br from-[#F58FA9] via-[#F9A968] to-[#AB8FBF] items-center justify-center p-10"
    >
      <!-- Transparent card with a rectangular shape -->
      <div class="bg-white bg-opacity-30 p-8 rounded-lg shadow-lg flex items-center justify-center"
           style="aspect-ratio: 2/1; max-width: 60%;">
        <p class="text-xl font-semibold" style="color: #643695B2;">
          "A journey of a thousand miles begins with a single step."
        </p>
      </div>
    </div>

    <!-- Login section with form taking most of the vertical space -->
    <div class="flex flex-col justify-between items-center w-full lg:w-1/2 bg-white p-4 sm:p-8 shadow-lg">
      <!-- Display the logo at the top -->
      <img src="../assets/logo.png" alt="Company Logo" class="w-32 mb-4" />

      <!-- Title and subtitle -->
      <div>
        <h2 class="text-3xl font-bold text-gray-700">Welcome Back</h2>
      </div>

      <!-- Form with spaced components -->
      <div class="flex flex-col justify-around flex-grow w-full sm:w-3/4 text-center">
        <!-- Email input with padding -->
        <div class="text-left">
          <label for="email" class="block text-sm font-medium text-gray-700">Email</label>
          <input
            v-model="email"
            type="email"
            id="email"
            class="mt-1 w-full border border-gray-300 rounded-md p-2 shadow-sm focus:border-blue-500 focus:ring focus:ring-blue-200"
            placeholder="Your email address"
          />
        </div>

        <!-- Password input with eye icon for visibility toggle -->
        <div class="relative text-left">
          <label for="password" class="block text-sm font-medium text-gray-700">Password</label>
          <input
            v-model="password"
            :type="passwordType"
            id="password"
            class="mt-1 w-full border border-gray-300 rounded-md p-2 pr-10 shadow-sm focus:border-blue-500 focus:ring focus:ring-blue-200"
            placeholder="Your password"
          />
          <!-- Eye icon to toggle password visibility -->
          <button
            @click="togglePasswordVisibility"
            class="absolute right-0 inset-y-0 flex items-center justify-center pr-3"
          >
            <i class="fas" :class="passwordType === 'password' ? 'fa-eye' : 'fa-eye-slash'"></i>
          </button>
          <!-- Forgot Password link -->
          <a href="#" class="text-sm text-gray-500 text-right absolute -bottom-6 right-0">Forgot Password?</a>
        </div>

        <!-- Continue button with increased vertical padding -->
        <div class="w-full mt-6">
          <button
            @click="login"
            class="w-full bg-blue-600 text-white py-4 px-4 rounded-md hover:bg-blue-700 focus:outline-none focus:ring focus:ring-blue-200"
          >
            Continue
          </button>
        </div>

        <!-- Divider with text -->
        <div class="mt-6 text-gray-500 text-sm">
          <span>or continue with</span>
        </div>

        <!-- Google and LinkedIn sign-in buttons with black text -->
        <div class="flex gap-4 w-full">
          <button
            @click="googleLogin"
            class="flex-1 bg-gray-200 text-black py-2 px-4 rounded-md hover:bg-gray-300 focus:outline-none focus:ring focus:ring-red-200"
          >
            Google
          </button>
          <button
            @click="linkedinLogin"
            class="flex-1 bg-gray-200 text-black py-2 px-4 rounded-md hover:bg-gray-300 focus:outline-none focus:ring focus:ring-blue-300"
          >
            LinkedIn
          </button>
        </div>

        <!-- Sign-up link -->
        <div class="mt-6 text-center text-sm text-gray-500">
          New to Coach Tribe? 
          <a href="#" class="text-blue-600 hover:text-blue-800">Sign Up</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const password = ref('');
const passwordType = ref('password');

const togglePasswordVisibility = () => {
  passwordType.value = passwordType.value === 'password' ? 'text' : 'password';
};

const login = () => {
  console.log('Logging in with:', email.value, password.value);
};

const googleLogin = () => {
  console.log('Google login');
};

const linkedinLogin = () => {
  console.log('LinkedIn login');
};
</script>

<style scoped>
/* Custom radial gradient background */
.radial-gradient {
  background: radial-gradient(circle at top left, #F05A8E, #F9A968, #643695);
}
</style>
