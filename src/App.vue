<script setup lang="ts">
import { ref } from 'vue'
import Carousel from './components/Carousel.vue'
import { ArrowRight, Menu } from 'lucide-vue-next'

const searchQuery = ref('')
const menuItems = [
  { label: 'Featured Channels', active: true },
  { label: 'My Channel' },
  { label: 'Studio' },
  { label: 'About' },
  { label: 'Terms' },
  { label: 'Privacy' }
]

// Featured creator channels
const carouselItems = [
  {
    id: 1,
    title: 'Angie',
    image: '/angie.png',
    url: '#'
  },
  {
    id: 2,
    title: '@2StrawsMMA',
    image: '/2straws.png',
    url: '#'
  },
  {
    id: 3,
    title: 'Creator Channel',
    image: 'https://picsum.photos/seed/creator3/300/400',
    url: '#'
  },
  {
    id: 4,
    title: 'Creator Channel',
    image: 'https://picsum.photos/seed/creator4/300/400',
    url: '#'
  },
  {
    id: 5,
    title: 'Creator Channel',
    image: 'https://picsum.photos/seed/creator5/300/400',
    url: '#'
  }
]
</script>

<template>
  <div class="relative min-h-screen w-full overflow-hidden">
    <!-- Background Image - Fixed -->
    <div
      class="fixed inset-0 z-0 bg-cover bg-center bg-no-repeat bg-linear-to-br from-cyan-950 via-cyan-600 to-cyan-500"
      style="background-image: url('/background.jpg')"
    >
      <!-- Overlay for better text readability -->
      <div class="absolute inset-0 bg-linear-to-b from-cyan-950/60 via-cyan-700/40 to-cyan-500/10"></div>
    </div>

    <!-- Content -->
    <div class="relative z-10 min-h-screen">
      <!-- Header -->
      <header class="p-6 flex items-center justify-between">
        <div class="flex items-center gap-2">
          <img src="/logo.png" alt="Open.Video" class="h-6 opacity-70" />
        </div>
        <button class="lg:hidden text-white p-2">
          <Menu class="w-6 h-6" />
        </button>
      </header>

      <!-- Main Content -->
      <main class="container mx-auto px-6 py-12">
        <div class="max-w-7xl mx-auto">
          <!-- Hero Section -->
          <div class="text-center mb-12">
            <h2 class="text-6xl md:text-7xl lg:text-[84px] font-bold mb-8 leading-tight">
              <span class="  bg-blend-color-burn bg-clip-text text-transparent bg-linear-to-r from-cyan-300/60 to-cyan-200/50">Search</span>
              <span class="text-white/70">Creator</span>
              <span class="bg-blend-color-burn bg-clip-text text-transparent bg-linear-to-r from-cyan-300/60 to-cyan-200/50">Channels</span>
            </h2>

            <!-- Search Bar -->
            <div class="max-w-2xl mx-auto relative">
              <input
                v-model="searchQuery"
                type="text"
                placeholder="search creators"
                class="w-full px-6 py-4 rounded-lg bg-white/90 backdrop-blur-sm text-gray-800 placeholder-gray-500 focus:outline-none focus:ring-2 focus:ring-cyan-400 pr-12"
              />
              <button class="absolute right-4 top-1/2 -translate-y-1/2 text-gray-600 hover:text-gray-800">
                <ArrowRight class="w-5 h-5" />
              </button>
            </div>
          </div>

          <!-- Content Grid -->
          <div class="grid lg:grid-cols-[300px_1fr] gap-12 items-start">
            <!-- Left Menu -->
            <nav class="hidden lg:block">
              <ul class="space-y-3">
                <li
                  v-for="(item, index) in menuItems"
                  :key="index"
                  class="text-right"
                >
                  <a
                    href="#"
                    :class="[
                      'text-2xl transition-colors',
                      item.active
                        ? 'text-white font-semibold'
                        : 'text-gray-300 hover:text-white font-normal'
                    ]"
                  >
                    {{ item.label }}
                  </a>
                </li>
              </ul>
            </nav>

            <!-- Carousel -->
            <div class="w-full">
              <Carousel :items="carouselItems" />
            </div>
          </div>
        </div>
      </main>
    </div>
  </div>
</template>

<style scoped>
/* Additional custom styles if needed */
</style>
