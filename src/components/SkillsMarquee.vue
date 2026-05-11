<script setup>
import { skills } from '../data/portfolio'

const marqueeSkills = [...skills, ...skills].map((skill, index) => ({
  ...skill,
  id: `${skill.name}-${index}`,
}))
</script>

<template>
  <section class="border-y border-line-soft bg-page-soft/80 py-8">
    <div class="flex w-max animate-marquee gap-4 px-8">
      <div
        v-for="skill in marqueeSkills"
        :key="skill.id"
        class="flex h-10 min-w-max items-center gap-3 rounded-full bg-chip px-5 text-sm font-medium text-text-main shadow-lg shadow-black/10"
      >
        <span class="grid h-5 w-5 place-items-center">
          <img
            :src="skill.iconUrl"
            :alt="`${skill.name} icon`"
            class="h-full w-full object-contain"
          />
        </span>
        {{ skill.name }}
      </div>
    </div>
  </section>
</template>
