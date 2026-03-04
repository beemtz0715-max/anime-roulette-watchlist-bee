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
    class="Oborder-slate-700/70 Obg-slate-900/60 rounded-3xl border p-5 shadow-2xl shadow-slate-950/30 backdrop-blur-sm"
  >
    <div v-if="props.loading">Loading ...</div>
    <div v-else>Done</div>
  </section>
</template>
