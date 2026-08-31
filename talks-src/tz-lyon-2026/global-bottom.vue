<script setup>
import { computed } from 'vue'
import { useSlideContext } from '@slidev/client'

const { $slidev } = useSlideContext()

const category = computed(() => $slidev.nav.currentFrontmatter?.category)
const categoryTag = computed(() => $slidev.nav.currentFrontmatter?.categoryTag ?? 'right')

const hashtag = computed(() => {
  if (!category.value) return ''
  return category.value
    .normalize('NFD')
    .replace(/[\u0300-\u036f]/g, '')
    .split(/[^a-zA-Z0-9]+/)
    .filter(Boolean)
    .map(word => word.charAt(0).toUpperCase() + word.slice(1).toLowerCase())
    .join('')
})

const positionClass = computed(() =>
  categoryTag.value === 'left' ? 'left-4' : 'right-4'
)
</script>

<template>
  <div
    v-if="category && categoryTag !== 'hide'"
    class="absolute bottom-4 text-sm opacity-50 z-50"
    :class="positionClass"
  >
    #{{ hashtag }}
  </div>
</template>
