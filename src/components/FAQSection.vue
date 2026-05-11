<script setup>
import { faqs } from '../data/portfolio'
import SectionEyebrow from './SectionEyebrow.vue'
</script>

<template>
  <section id="contact" class="scroll-mt-24 py-24 lg:py-32">
    <div class="mx-auto grid w-full max-w-7xl gap-14 px-6 lg:grid-cols-2 lg:px-10">
      <div>
        <SectionEyebrow label="FAQs" />
        <h2 class="mt-5 text-5xl font-black leading-tight tracking-normal md:text-6xl">
          Have<br />
          Questions?
        </h2>
      </div>

      <div class="space-y-4">
        <details
          v-for="(faq, index) in faqs"
          :key="faq.question"
          class="group rounded-2xl border border-line-soft bg-panel-soft px-5 py-5"
        >
          <summary class="flex cursor-pointer list-none items-center justify-between gap-6 text-base font-bold text-text-main">
            <span><span class="mr-3 text-text-muted">{{ String(index + 1).padStart(2, '0') }}.</span>{{ faq.question }}</span>
            <svg class="h-4 w-4 shrink-0 transition group-open:rotate-180" viewBox="0 0 24 24" fill="none" aria-hidden="true">
              <path d="m6 9 6 6 6-6" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" />
            </svg>
          </summary>
          <p class="mt-4 max-w-3xl pl-9 text-sm leading-6 text-text-muted">{{ faq.answer }}</p>
        </details>
      </div>
    </div>
  </section>
</template>
