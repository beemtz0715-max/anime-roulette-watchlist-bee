<script setup>
import { computed } from 'vue'
import AnimeCard from '@/components/AnimeCard.vue'
import { useAnimeRoulette } from '@/composables/useAnimeRoulette'

const { anime, loading, error, spin, cooldownLeft } = useAnimeRoulette()

const spinDisabled = computed(() => loading.value || cooldownLeft.value > 0)

const spinLabel = computed(() => {
  if (loading.value) return 'Spinning...'
  if (cooldownLeft.value > 0) return `Cooldown ${cooldownLeft.value}s`
  return 'SPIN 🎰'
})
</script>

<template>
  <main class="space-y-4 p-5">
    <div class="container mx-auto space-y-4">
      <div class="flex flex-col items-center gap-4">
        <button
          type="button"
          class="cursor-pointer rounded-full border border-cyan-300/70 bg-cyan-400/20 px-6 py-3 text-base font-black tracking-wide text-cyan-100 hover:bg-cyan-400/30 disabled:cursor-not-allowed disabled:opacity-60"
          :disabled="spinDisabled"
          @click="spin"
        >
          {{ spinLabel }}
        </button>

        <p
          v-if="cooldownLeft > 0"
          class="mt-4 rounded-xl border border-amber-300/50 bg-amber-400/10 px-3 py-2 text-sm font-semibold text-amber-100"
        >
          Rate-limited. Try again in {{ cooldownLeft }}s.
        </p>
      </div>

      <AnimeCard
        :loading="loading"
        :error="error"
        :anime="anime"
      />
    </div>
  </main>
</template>
