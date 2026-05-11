<script setup>
import { projects } from '../data/portfolio'
import SectionEyebrow from './SectionEyebrow.vue'
</script>

<template>
  <section id="projects" class="scroll-mt-24 py-24 lg:py-32">
    <div class="mx-auto w-full max-w-7xl px-6 lg:px-10">
      <SectionEyebrow label="My Work" />
      <h2 class="mt-5 text-5xl font-black leading-none tracking-normal md:text-6xl">
        Selected Projects
      </h2>
      <p class="mt-5 max-w-2xl text-base leading-7 text-text-muted">
        Here's a curated selection showcasing my expertise and the achieved results.
      </p>

      <div class="mt-16 grid gap-x-16 gap-y-14 lg:grid-cols-2">
        <article v-for="project in projects" :key="project.title">
          <div class="grid aspect-video place-items-center overflow-hidden rounded-3xl bg-panel-soft">
            <img
              v-if="project.iconUrl"
              :src="project.iconUrl"
              :alt="`${project.title} preview`"
              class="h-full w-full object-cover"
            />
            <span v-else class="text-sm font-semibold text-text-muted">Add project image URL</span>
          </div>

          <div class="mt-5 flex items-end justify-between gap-5">
            <div>
              <h3 class="text-2xl font-black text-text-main">{{ project.title }}</h3>
              <div class="mt-4 flex flex-wrap gap-3">
                <span
                  v-for="tag in project.tags"
                  :key="tag"
                  class="rounded-full bg-chip px-4 py-2 text-sm font-medium text-text-main"
                >
                  {{ tag }}
                </span>
              </div>
            </div>
            <p class="text-base font-semibold text-text-muted">{{ project.year }}</p>
          </div>
        </article>
      </div>
    </div>
  </section>
</template>
