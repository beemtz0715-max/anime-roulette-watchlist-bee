<script setup>
const props = defineProps({
  anime: {
    type: Object,
    default: null,
  },
  loading: {
    type: Boolean,
    default: false,
  },
  error: {
    type: String,
    default: '',
  },
  inWatchlist: {
    type: Boolean,
    default: false,
  },
})
</script>

<template>
  <section
    class="rounded-3xl border border-slate-700/70 bg-slate-900/60 p-5 shadow-2xl shadow-slate-950/30 backdrop-blur-sm"
  >
    <div
      v-if="loading"
      class="h-72 animate-pulse rounded-2xl bg-slate-800"
    ></div>

    <div
      v-else-if="error"
      class="rounded-2xl border border-red-300/50 bg-red-500/10 p-4 text-red-100"
    >
      <h3 class="text-lg font-semibold">Spin failed</h3>
      <p class="mt-2 text-sm text-red-100/90">{{ error }}</p>
    </div>

    <div v-else-if="anime">
      <pre>{{ anime }}</pre>
    </div>

    <div
      v-else
      class="rounded-2xl border border-slate-700/60 bg-slate-800/50 p-6 text-center text-slate-300"
    >
      Pull the lever to request your first random anime.
    </div>
  </section>
</template>
