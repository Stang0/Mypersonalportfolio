<script setup>
defineProps({
  label: {
    type: String,
    required: true,
  },
})
</script>

<template>
  <p class="flex items-center gap-3 text-sm font-semibold uppercase tracking-wide text-primary">
    <span class="material-symbols-rounded text-base" aria-hidden="true">auto_awesome</span>
    {{ label }}
  </p>
</template>
