<script setup>
import { awards } from '../data/portfolio'
import SectionEyebrow from './SectionEyebrow.vue'
</script>

<template>
  <section class="py-24 lg:py-32">
    <div class="mx-auto grid w-full max-w-7xl gap-14 px-6 lg:grid-cols-2 lg:px-10">
      <div>
        <SectionEyebrow label="Awards" />
        <h2 class="mt-5 text-5xl font-black leading-tight tracking-normal md:text-6xl">
          Awards &amp;<br />
          Recognition
        </h2>
      </div>

      <div class="divide-y divide-line-soft">
        <article
          v-for="award in awards"
          :key="award.title"
          class="flex items-center justify-between gap-6 py-6 first:pt-0"
        >
          <h3 class="text-lg font-bold text-text-main">{{ award.title }}</h3>
          <p class="min-w-max text-sm font-semibold text-text-muted">{{ award.date }}</p>
        </article>
      </div>
    </div>
  </section>
</template>
