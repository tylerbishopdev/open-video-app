<script setup lang="ts">
import { ref } from 'vue'

interface CarouselItem {
  id: number
  title: string
  image: string
  url: string
}

defineProps<{
  items: CarouselItem[]
}>()

const hoveredIndex = ref<number | null>(null)
</script>

<template>
  <div class="flex gap-2 w-full h-[500px]">
    <div
      v-for="(item, index) in items"
      :key="item.id"
      @mouseenter="hoveredIndex = index"
      @mouseleave="hoveredIndex = null"
      :style="{
        flex: hoveredIndex === index ? '3' : '1',
      }"
      class="relative overflow-hidden rounded-3xl transition-all duration-700 ease-out cursor-pointer group"
    >
      <img
        :src="item.image"
        :alt="item.title"
        class="absolute inset-0 w-full h-full object-cover"
      />

      <!-- Dark overlay -->
      <div class="absolute inset-0 bg-black/40 group-hover:bg-black/20 transition-all duration-700"></div>

      <!-- Content -->
      <div class="absolute bottom-0 left-0 right-0 p-8">
        <div class="flex items-center gap-4">
          <div class="w-14 h-14 rounded-full bg-cyan-500/20 backdrop-blur-md border-2 border-cyan-400/40 flex items-center justify-center flex-shrink-0">
            <svg class="w-7 h-7 text-cyan-300" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <circle cx="12" cy="8" r="4" stroke-width="2"/>
              <path d="M6 21v-2a4 4 0 0 1 4-4h4a4 4 0 0 1 4 4v2" stroke-width="2" stroke-linecap="round"/>
            </svg>
          </div>

          <div
            class="transition-all duration-700"
            :class="hoveredIndex === index ? 'opacity-100' : 'opacity-0'"
          >
            <p class="text-white font-bold text-xl">{{ item.title }}</p>
            <p class="text-cyan-300 text-base">2strawsmma.com</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
