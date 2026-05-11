<script setup>
import { educationPath } from '../data/portfolio'
import SectionEyebrow from './SectionEyebrow.vue'
</script>

<template>
  <section id="education" class="scroll-mt-24 border-t border-line-soft py-24 lg:py-32">
    <div class="mx-auto grid w-full max-w-7xl gap-14 px-6 lg:grid-cols-2 lg:px-10">
      <div>
        <SectionEyebrow label="Education Path" />
        <h2 class="mt-5 text-5xl font-black leading-none tracking-normal md:text-6xl">
          Education
        </h2>
        <p class="mt-7 max-w-md text-base leading-7 text-text-muted">
          My learning path combines university study, practical frontend projects, and continuous design exploration.
        </p>
      </div>

      <div class="divide-y divide-line-soft">
        <article
          v-for="item in educationPath"
          :key="item.school"
          class="flex flex-col gap-5 py-6 first:pt-0 sm:flex-row sm:items-center"
        >
          <div class="grid h-12 w-12 place-items-center overflow-hidden rounded-full  text-xs font-black text-white">
            <img
              v-if="item.iconUrl"
              :src="item.iconUrl"
              :alt="`${item.school} logo`"
              class="h-full w-full object-cover"
            />
            <span v-else>{{ item.school.slice(0, 2).toUpperCase() }}</span>
          </div>
          <div class="flex-1">
            <h3 class="text-lg font-bold text-text-main">{{ item.school }}</h3>
            <p class="mt-1 font-semibold text-text-muted">{{ item.program }}</p>
          </div>
          <p class="text-sm font-semibold text-text-muted sm:text-right">{{ item.period }}</p>
        </article>

        <button class="mx-auto mt-7 block text-sm font-bold text-text-main transition hover:text-primary">
          Show More
        </button>
      </div>
    </div>
  </section>
</template>
