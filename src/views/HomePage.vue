<script setup>
import AnimeCard from '@/components/AnimeCard.vue'
const spin = () => {
  console.log('Hello')
}
</script>

<template>
  <main
    class="min-h-screen bg-[radial-gradient(circle_at_15%_20%,#334155,transparent_40%),radial-gradient(circle_at_85%_0%,#0f766e,transparent_40%)]"
  >
    <div class="mx-auto max-w-7xl">
      <header class="mb-8"></header>

      <div class="grid gap-6 lg:grid-cols-[1.2fr_0.8fr]">
        <section class="space-y-5">
          <div
            class="rounded-3xl border border-slate-700/70 bg-slate-900/60 p-5 shadow-2xl shadow-slate-950/30 backdrop-blur"
          >
            <div class="flex flex-col gap-3 sm:flex-row sm:items-center sm:justify-between">
              <div>
                <h2 class="text-xl font-bold text-white">Roulette</h2>
                <p class="text-sm text-slate-300">
                  Pull the lever for your next random anime recommendation.
                </p>
              </div>

              <button
                type="button"
                class="cursor-pointer rounded-full border border-cyan-300/70 bg-cyan-400/20 px-6 py-3 text-base font-black"
                @click="spin"
              >
                Spin
              </button>
            </div>
          </div>
        </section>
      </div>
    </div>
  </main>
</template>
