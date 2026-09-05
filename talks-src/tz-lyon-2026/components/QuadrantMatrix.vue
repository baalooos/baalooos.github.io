<script setup>
defineProps({
  highlight: {
    type: String,
    default: null, // 'known-known' | 'known-unknown' | 'unknown-known' | 'unknown-unknown'
  },
})

const quadrants = [
  { key: 'known-known', label: 'Known Known' },
  { key: 'known-unknown', label: 'Known Unknown' },
  { key: 'unknown-known', label: 'Unknown Known' },
  { key: 'unknown-unknown', label: 'Unknown Unknown' },
]
</script>

<template>
  <div class="grid grid-cols-2 gap-4 mt-8">
    <div
      v-for="q in quadrants"
      :key="q.key"
      class="border-2 rounded-lg p-8 text-center transition-all duration-300"
      :class="highlight && highlight !== q.key ? 'opacity-30' : ''"
      :style="highlight === q.key
        ? { borderColor: 'var(--slidev-theme-primary)', backgroundColor: 'color-mix(in srgb, var(--slidev-theme-primary) 10%, transparent)' }
        : {}"
    >
      <div class="text-xl" :class="highlight === q.key ? 'font-bold' : 'font-semibold'">
        {{ q.label }}
      </div>
    </div>
  </div>
</template>
