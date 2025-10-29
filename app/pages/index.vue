<script setup lang="ts">
const email = ref('')
</script>

<template>
  <div class="relative min-h-screen w-full overflow-hidden">
    <!-- Background Image -->
    <div class="absolute inset-0">
      <img
        src="/images/background.png"
        alt="Background"
        class="w-full h-full object-cover"
      >
    </div>

    <!-- Logo -->
    <NuxtLink to="/" class="absolute top-6 left-[6%]">
      <img
        src="/images/logo.png"
        alt="RATIONAL Logo"
        class="h-12 w-auto cursor-pointer hover:opacity-90 transition-opacity"
      >
    </NuxtLink>

    <!-- Main Content -->
    <div class="relative flex min-h-screen items-center justify-between px-[6%] xl:px-[8%] 2xl:px-[12%]">
      <!-- Left Section - Hero Text -->
      <div class="flex flex-col max-w-2xl text-white">
        <h1 class="text-6xl font-bold leading-tight mb-6">
          Analyze device behavior<br>over time
        </h1>
        <p class="text-3xl font-light">
          With RITA – based on log files.<br>Simple. Fast. Traceable.
        </p>
      </div>

      <!-- Right Section - Login Card -->
      <div class="backdrop-blur-sm bg-white/90 rounded-xl p-9 w-[440px] shadow-2xl">
        <!-- Language Selector -->
        <div class="flex justify-end mb-16">
          <button class="flex items-center gap-1 text-sm text-natural-700 border-b border-natural-700 pb-1">
            <span>English</span>
            <UIcon name="i-lucide-chevron-down" class="w-5 h-5" />
          </button>
        </div>

        <!-- RITA Title -->
        <h2 class="text-3xl font-bold text-natural-700 mb-24">
          RITA
        </h2>

        <!-- Login Form -->
        <div class="space-y-8">
          <div>
            <h3 class="text-xl text-natural-700 mb-8">
              Login
            </h3>

            <div class="space-y-9">
              <!-- Email Input -->
              <div class="space-y-2 w-full">
                <UInput
                  v-model="email"
                  type="email"
                  placeholder="Enter your email"
                  size="xl"              
                  :ui="{
                    base: 'h-12 bg-natural-200 border-natural-700 w-full text-natural-700 ',
                  }"
                  class="w-full"

                />

                <!-- Register Link -->
                <div class="flex items-center gap-3.5 text-sm">
                  <span class="text-natural-700">Don't have an account?</span>
                  <NuxtLink to="/register" class="text-rational-red hover:underline">
                    Register here.
                  </NuxtLink>
                </div>
              </div>

              <!-- Login Button -->
              <NuxtLink to="/home" class="block w-full">
                <UButton
                  block
                  size="xl"
                  class="h-12 bg-rational-red hover:bg-rational-red/90 text-white font-bold w-full"
                >
                  Log in
                </UButton>
              </NuxtLink>
            </div>
          </div>

          <!-- Footer Links -->
          <div class="flex items-center justify-center gap-20 text-sm text-natural-500 pt-32">
            <NuxtLink to="/data-protection" class="hover:underline">
              Data Protection
            </NuxtLink>
            <NuxtLink to="/imprint" class="hover:underline">
              Imprint
            </NuxtLink>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
