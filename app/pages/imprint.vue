<script setup lang="ts">
useSeoMeta({
  title: 'Imprint - RITA',
  description: 'Legal information and imprint for RITA Kitchen Equipment Monitoring'
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
        Imprint
      </h1>

      <div class="bg-white rounded-lg shadow-sm p-8 space-y-6">
        <section>
          <h2 class="text-2xl font-semibold text-natural-700 mb-4">
            Company Information
          </h2>
          <div class="text-natural-500 leading-relaxed space-y-2">
            <p class="font-semibold text-natural-700">
              RATIONAL AG
            </p>
            <p>Siegfried-Meister-Straße 1</p>
            <p>86899 Landsberg am Lech</p>
            <p>Germany</p>
          </div>
        </section>

        <section>
          <h2 class="text-2xl font-semibold text-natural-700 mb-4">
            Contact
          </h2>
          <div class="text-natural-500 leading-relaxed space-y-2">
            <p>
              <span class="font-medium text-natural-700">Phone:</span>
              <a
                href="tel:+498191327-0"
                class="text-rational-red hover:underline ml-2"
              >
                +49 (0) 8191 327-0
              </a>
            </p>
            <p>
              <span class="font-medium text-natural-700">Fax:</span>
              <span class="ml-2">+49 (0) 8191 327-272</span>
            </p>
            <p>
              <span class="font-medium text-natural-700">Email:</span>
              <a
                href="mailto:info@rational-online.com"
                class="text-rational-red hover:underline ml-2"
              >
                info@rational-online.com
              </a>
            </p>
            <p>
              <span class="font-medium text-natural-700">Website:</span>
              <a
                href="https://www.rational-online.com"
                target="_blank"
                class="text-rational-red hover:underline ml-2"
              >
                www.rational-online.com
              </a>
            </p>
          </div>
        </section>

        <section>
          <h2 class="text-2xl font-semibold text-natural-700 mb-4">
            Legal Information
          </h2>
          <div class="text-natural-500 leading-relaxed space-y-2">
            <p>
              <span class="font-medium text-natural-700">Register Court:</span>
              <span class="ml-2">Augsburg District Court</span>
            </p>
            <p>
              <span class="font-medium text-natural-700">Registration Number:</span>
              <span class="ml-2">HRB 2831</span>
            </p>
            <p>
              <span class="font-medium text-natural-700">VAT ID:</span>
              <span class="ml-2">DE 127 308 856</span>
            </p>
          </div>
        </section>

        <section>
          <h2 class="text-2xl font-semibold text-natural-700 mb-4">
            Board of Management
          </h2>
          <div class="text-natural-500 leading-relaxed">
            <p>Dr. Peter Stadelmann (CEO)</p>
            <p>Axel Kaufmann (CFO)</p>
            <p>Walter Kurtz (COO)</p>
          </div>
        </section>

        <section>
          <h2 class="text-2xl font-semibold text-natural-700 mb-4">
            Supervisory Board
          </h2>
          <div class="text-natural-500 leading-relaxed">
            <p>Dr. Hans Maerz (Chairman)</p>
          </div>
        </section>

        <section>
          <h2 class="text-2xl font-semibold text-natural-700 mb-4">
            Disclaimer
          </h2>
          <p class="text-natural-500 leading-relaxed">
            The content of this website has been compiled with meticulous care and to the best of our knowledge. However, we cannot assume any liability for the up-to-dateness, completeness or accuracy of any of the pages. We reserve the right to change or supplement the information provided without prior notice.
          </p>
        </section>

        <section>
          <h2 class="text-2xl font-semibold text-natural-700 mb-4">
            Copyright
          </h2>
          <p class="text-natural-500 leading-relaxed">
            All content, including images, graphics, and text, is protected by copyright. Any use, particularly reproduction or distribution, without the prior written consent of RATIONAL AG is prohibited.
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
