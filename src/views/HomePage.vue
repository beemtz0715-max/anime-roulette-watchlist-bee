<script setup>
import AnimeCard from '@/components/AnimeCard.vue'
import { useAnimeRoulette } from '@/composables/useAnimeRoulette'

const { anime, loading, error, spin, cooldownLeft } = useAnimeRoulette()
</script>

<template>
  <main class="space-y-4 p-5">
    <button
      class="rounded bg-cyan-500 px-4 py-2 text-white hover:bg-cyan-600"
      @click="spin"
      :disabled="loading || cooldownLeft > 0"
    >
      Spin Anime
      <span v-if="cooldownLeft > 0"> (Wait {{ cooldownLeft }}s)</span>
    </button>

    <AnimeCard
      :loading="loading"
      :error="error"
      :anime="anime"
    />
  </main>
</template>
