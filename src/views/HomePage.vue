<script setup>
import { ref } from 'vue'
import AnimeCard from '@/components/AnimeCard.vue'

const loading = ref(false)
const error = ref('')

const spin = () => {
  console.log('Hello')
  if (error.value.length > 0) {
    error.value = ''
  } else {
    error.value = 'Something wrong'
  }
}
</script>

<template>
  <main class="p-5">
    <div class="container mx-auto">
      <div class="space-y-4">
        <button
          type="button"
          class="rounded bg-cyan-500 px-4 py-2 text-white hover:bg-cyan-600"
          @click="spin"
        >
          Spin Anime
        </button>

        <section class="space-y-4">
          <AnimeCard :loading="true" />
          <AnimeCard
            :loading="loading"
            :error="error"
          />

          <section
            class="rounded-2xl border border-slate-700/60 bg-slate-800/50 p-6 text-center text-slate-300"
          >
            <div
              v-if="error"
              class="rounded-2xl border border-red-300/50 bg-red-500/10 p-4 text-red-100"
            >
              <h3 class="text-lg font-semibold">Spin failed</h3>
              <p class="mt-2 text-sm text-red-100/90">{{ error }}</p>
            </div>

            <div v-else-if="loading">Loading...</div>

            <div v-else>Pull the lever to request your first random anime.</div>
          </section>
        </section>
      </div>
    </div>
  </main>
</template>
