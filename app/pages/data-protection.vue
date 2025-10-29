<script setup lang="ts">
useSeoMeta({
  title: 'Data Protection - RITA',
  description: 'Data protection and privacy policy for RITA Kitchen Equipment Monitoring'
})
</script>

<template>
  <div class="min-h-screen bg-gray-50">
    <!-- Header -->
    <header class="bg-white border-b border-gray-200 px-8 py-4">
      <div class="flex items-center justify-between">
        <NuxtLink
          to="/"
          class="flex items-center gap-4"
        >
          <img
            src="/images/logo.png"
            alt="RATIONAL Logo"
            class="h-8 cursor-pointer hover:opacity-90 transition-opacity"
          >
          <span class="text-rational-red font-bold text-lg">Combilyzer</span>
        </NuxtLink>

        <NuxtLink to="/">
          <UButton
            icon="i-lucide-x"
            variant="ghost"
            color="neutral"
          >
            Close
          </UButton>
        </NuxtLink>
      </div>
    </header>

    <!-- Main Content -->
    <div class="max-w-4xl mx-auto px-8 py-12">
      <h1 class="text-4xl font-bold text-natural-700 mb-8">
        Data Protection
      </h1>

      <div class="bg-white rounded-lg shadow-sm p-8 space-y-6">
        <section>
          <h2 class="text-2xl font-semibold text-natural-700 mb-4">
            1. Data Protection at a Glance
          </h2>
          <p class="text-natural-500 leading-relaxed">
            The following information provides a simple overview of what happens to your personal data when you use our service. Personal data is any data that can be used to identify you personally.
          </p>
        </section>

        <section>
          <h2 class="text-2xl font-semibold text-natural-700 mb-4">
            2. Data Collection
          </h2>
          <p class="text-natural-500 leading-relaxed mb-4">
            We collect data that you provide to us when using the RITA Combilyzer system. This includes:
          </p>
          <ul class="list-disc list-inside text-natural-500 space-y-2 ml-4">
            <li>Email addresses for login purposes</li>
            <li>Device serial numbers and log files</li>
            <li>Report data and analysis results</li>
            <li>Usage statistics and system interactions</li>
          </ul>
        </section>

        <section>
          <h2 class="text-2xl font-semibold text-natural-700 mb-4">
            3. How We Use Your Data
          </h2>
          <p class="text-natural-500 leading-relaxed">
            Your data is used solely for the purpose of providing and improving the RITA service. We analyze device behavior to help you maintain and optimize your kitchen equipment. Your data is stored securely and is not shared with third parties without your consent.
          </p>
        </section>

        <section>
          <h2 class="text-2xl font-semibold text-natural-700 mb-4">
            4. Your Rights
          </h2>
          <p class="text-natural-500 leading-relaxed mb-4">
            You have the right to:
          </p>
          <ul class="list-disc list-inside text-natural-500 space-y-2 ml-4">
            <li>Access your personal data</li>
            <li>Request correction of inaccurate data</li>
            <li>Request deletion of your data</li>
            <li>Withdraw consent at any time</li>
            <li>Lodge a complaint with a supervisory authority</li>
          </ul>
        </section>

        <section>
          <h2 class="text-2xl font-semibold text-natural-700 mb-4">
            5. Contact
          </h2>
          <p class="text-natural-500 leading-relaxed">
            For any questions regarding data protection, please contact us at:
            <a
              href="mailto:privacy@rational-online.com"
              class="text-rational-red hover:underline ml-1"
            >
              privacy@rational-online.com
            </a>
          </p>
        </section>

        <div class="pt-8 border-t border-gray-200">
          <p class="text-sm text-natural-500">
            Last updated: January 2025
          </p>
        </div>
      </div>

      <div class="mt-8 text-center">
        <NuxtLink to="/">
          <UButton
            icon="i-lucide-arrow-left"
            variant="outline"
            color="neutral"
          >
            Back to Home
          </UButton>
        </NuxtLink>
      </div>
    </div>
  </div>
</template>
