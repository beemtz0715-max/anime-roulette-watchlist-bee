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
    <!-- Loading state -->
    <div v-if="loading">Loading ...</div>

    <!-- Error state -->
    <div v-else-if="error">Error: {{ error }}</div>

    <!-- Success / main content -->
    <div v-else>Done</div>
  </section>
</template>
