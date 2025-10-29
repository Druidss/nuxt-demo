<script setup lang="ts">
import { h, resolveComponent } from 'vue'
import type { TableColumn } from '@nuxt/ui'

const UBadge = resolveComponent('UBadge')
const UIcon = resolveComponent('UIcon')
const UButton = resolveComponent('UButton')
const UDropdown = resolveComponent('UDropdown')

type Report = {
  id: string
  title: string
  serialNumber: string
  status: 'success' | 'error'
  dates: string
  xmlDatum: string
  aweDaterange: string
  created: string
}

// Dummy data matching Figma design
const data = ref<Report[]>([
  {
    id: '1',
    title: 'TestProd',
    serialNumber: 'E61S2221030093D4',
    status: 'error',
    dates: 'AWE, XML',
    xmlDatum: '16.06.2023 (16:26:28)',
    aweDaterange: '15.12.2023 - 23.12.2023',
    created: '09.04.2025 (14:12:25)'
  },
  {
    id: '2',
    title: 'Sollte funktionieren',
    serialNumber: 'E61S2230931086691',
    status: 'success',
    dates: 'XML',
    xmlDatum: '19.01.2024 (12:09:05)',
    aweDaterange: '-',
    created: '27.03.2025 (17:37:55)'
  },
  {
    id: '3',
    title: 'Dsw2',
    serialNumber: 'E61S2221030093D4',
    status: 'success',
    dates: 'XML',
    xmlDatum: '16.06.2023 (16:26:28)',
    aweDaterange: '-',
    created: '20.08.2024 (10:20:20)'
  },
  {
    id: '4',
    title: 'Double AWE',
    serialNumber: 'E61S2221030093D4',
    status: 'success',
    dates: 'AWE, XML',
    xmlDatum: '16.09.2023 (16:26:28)',
    aweDaterange: '15.12.2023 - 15.12.2023',
    created: '23.07.2024 (10:59:35)'
  },
  {
    id: '5',
    title: 'double XML',
    serialNumber: 'E61S2230931086691',
    status: 'error',
    dates: 'XML',
    xmlDatum: '19.01.2024 (12:09:05)',
    aweDaterange: '01.06.2023 - 09.07.2023',
    created: '23.07.2024 (10:59:35)'
  },
  {
    id: '6',
    title: 'Erster',
    serialNumber: 'G61S120122865130',
    status: 'success',
    dates: 'AWE, XML',
    xmlDatum: '24.03.2024 (12:31:12)',
    aweDaterange: '09.07.2024 - 15.07.2024',
    created: '18.07.2024 (10:07:48)'
  },
  {
    id: '7',
    title: 'Erster',
    serialNumber: 'G61S120122865130',
    status: 'success',
    dates: 'AWE, XML',
    xmlDatum: '24.03.2024 (12:31:12)',
    aweDaterange: '09.07.2024 - 15.07.2024',
    created: '18.07.2024 (10:07:48)'
  }
])

const searchQuery = ref('')

// Filter reports based on search query
const filteredData = computed(() => {
  if (!searchQuery.value) return data.value

  const query = searchQuery.value.toLowerCase()
  return data.value.filter(report =>
    report.title.toLowerCase().includes(query) ||
    report.serialNumber.toLowerCase().includes(query)
  )
})

// Define columns using official format
const columns: TableColumn<Report>[] = [
  {
    accessorKey: 'title',
    header: 'Title',
    cell: ({ row }) => row.getValue('title')
  },
  {
    accessorKey: 'serialNumber',
    header: 'Seriennummer',
    cell: ({ row }) => row.getValue('serialNumber')
  },
  {
    accessorKey: 'status',
    header: 'Status',
    cell: ({ row }) => {
      const status = row.getValue('status') as string
      const color = status === 'success' ? 'success' : 'error'
      const icon = status === 'success' ? 'i-lucide-check-circle' : 'i-lucide-alert-triangle'

      return h(UBadge, { variant: 'subtle', color, size: 'xs' }, () =>
        h(UIcon, { name: icon, class: 'w-4 h-4' })
      )
    }
  },
  {
    accessorKey: 'dates',
    header: 'Daten',
    cell: ({ row }) => row.getValue('dates')
  },
  {
    accessorKey: 'xmlDatum',
    header: 'XML Datum',
    cell: ({ row }) => {
      const value = row.getValue('xmlDatum') as string
      return h('div', { class: 'whitespace-pre-line text-sm' }, value)
    }
  },
  {
    accessorKey: 'aweDaterange',
    header: 'AWE Daterange',
    cell: ({ row }) => row.getValue('aweDaterange')
  },
  {
    accessorKey: 'created',
    header: 'Created',
    cell: ({ row }) => {
      const value = row.getValue('created') as string
      return h('div', { class: 'whitespace-pre-line text-sm' }, value)
    }
  },
  {
    accessorKey: 'actions',
    header: '',
    cell: ({ row }) => {
      return h(UDropdown, {
        items: [
          [{ label: 'Edit', icon: 'i-lucide-pencil' }],
          [{ label: 'Delete', icon: 'i-lucide-trash-2', color: 'red' }]
        ]
      }, () =>
        h(UButton, {
          icon: 'i-lucide-more-vertical',
          variant: 'ghost',
          color: 'neutral',
          size: 'sm'
        })
      )
    }
  }
]
</script>

<template>
  <div class="min-h-screen bg-gray-50">
    <!-- Header -->
    <header class="bg-white border-b border-gray-200 px-8 py-4">
      <div class="flex items-center justify-between">
        <NuxtLink to="/" class="flex items-center gap-4">
          <img src="/images/logo.png" alt="RATIONAL Logo"
            class="h-8 cursor-pointer hover:opacity-90 transition-opacity">
          <span class="text-rational-red font-bold text-lg">Combilyzer</span>
        </NuxtLink>

        <div class="flex items-center gap-4">
          <UButton icon="i-lucide-rotate-ccw" variant="ghost" color="neutral" />
          <UButton icon="i-lucide-help-circle" variant="ghost" color="neutral" />
          <UButton icon="i-lucide-bell" variant="ghost" color="neutral" />
          <UAvatar src="https://i.pravatar.cc/150?u=user" size="sm" />
        </div>
      </div>
    </header>

    <!-- Main Content -->
    <div class="px-8 py-6">
      <!-- Welcome Section -->
      <div class="mb-8">
        <h1 class="text-rational-red text-2xl font-bold mb-2">
          Willkommen beim RITA
        </h1>
        <h2 class="text-natural-700 text-3xl font-normal">
          Hallo, Florian Goth, Goth Florian
        </h2>
      </div>

      <!-- Reports Section -->
      <div class="bg-white rounded-lg shadow-sm">
        <div class="p-6 border-b border-gray-200">
          <div class="flex items-center justify-between">
            <h3 class="text-2xl font-semibold text-natural-700">Reports</h3>
            <UButton icon="i-lucide-plus" class="bg-rational-red hover:bg-rational-red/90 text-white" size="lg">
              Create New Report
            </UButton>
          </div>
        </div>

        <div class="p-6">
          <!-- Search and Actions -->
          <div class="flex items-center justify-between mb-6">
            <UInput v-model="searchQuery" icon="i-lucide-search" placeholder="Search a report" class="w-80" :ui="{
              base: 'h-8 bg-white border-natural-700 w-full text-natural-700',
            }" />

            <div class="flex items-center gap-2">
              <UButton icon="i-lucide-pencil" variant="ghost" color="neutral" />
              <UButton icon="i-lucide-list-filter" variant="ghost" color="neutral" />
              <UButton icon="i-lucide-mail" variant="ghost" color="neutral" />
              <UButton icon="i-lucide-download" variant="ghost" color="neutral" />
              <UButton icon="i-lucide-trash-2" variant="ghost" color="neutral" />
            </div>
          </div>

          <!-- Table -->
          <UTable :data="filteredData" :columns="columns" />
        </div>
      </div>
    </div>
  </div>
</template>
