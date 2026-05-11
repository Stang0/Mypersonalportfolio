<script setup>
import { computed, onBeforeUnmount, onMounted, ref } from 'vue'
import { navItems } from '../data/portfolio'

const theme = ref('dark')
const isScrolled = ref(false)

const isDark = computed(() => theme.value === 'dark')

const applyTheme = (nextTheme) => {
  theme.value = nextTheme
  document.documentElement.dataset.theme = nextTheme
  localStorage.setItem('theme', nextTheme)
}

const toggleTheme = () => {
  applyTheme(isDark.value ? 'light' : 'dark')
}

const updateScrollState = () => {
  isScrolled.value = window.scrollY > 16
}

onMounted(() => {
  const savedTheme = localStorage.getItem('theme')
  const prefersDark = window.matchMedia('(prefers-color-scheme: dark)').matches

  applyTheme(savedTheme || (prefersDark ? 'dark' : 'light'))
  updateScrollState()
  window.addEventListener('scroll', updateScrollState)
})

onBeforeUnmount(() => {
  window.removeEventListener('scroll', updateScrollState)
})
</script>

<template>
  <header
    class="fixed left-1/2 top-4 z-50 flex h-14 -translate-x-1/2 items-center justify-between rounded-full border transition-all duration-500 ease-out"
    :class="isScrolled
      ? 'w-11/12 max-w-3xl border-line-soft bg-panel/70 px-5 shadow-2xl shadow-black/15 backdrop-blur-xl md:px-6'
      : 'w-11/12 max-w-7xl border-transparent bg-transparent px-6 shadow-none backdrop-blur-0 md:px-10'"
  >
    <a href="#" class="text-xl font-black tracking-tight">Portfolio</a>

    <nav
      class="hidden items-center text-sm text-text-muted transition-all duration-500 ease-out md:flex"
      :class="isScrolled ? 'gap-6' : 'gap-8'"
    >
      <a
        v-for="item in navItems"
        :key="item.href"
        :href="item.href"
        class="flex items-center gap-3 transition hover:text-text-main"
        :class="{ 'font-medium text-text-main': item.label === 'About' }"
      >
        <span v-if="item.label === 'About'" class="h-1.5 w-1.5 rounded-full bg-primary"></span>
        {{ item.label }}
      </a>
    </nav>

    <button
      type="button"
      :aria-label="isDark ? 'Switch to light mode' : 'Switch to dark mode'"
      class="grid h-10 w-10 place-items-center rounded-full text-text-main transition hover:bg-chip"
      @click="toggleTheme"
    >
      <span class="material-symbols-rounded" aria-hidden="true">
        {{ isDark ? 'dark_mode' : 'light_mode' }}
      </span>
    </button>
  </header>
</template>
