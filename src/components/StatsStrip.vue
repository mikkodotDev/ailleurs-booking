<template>
  <div class="stats-strip">
    <div v-for="stat in stats" :key="stat.id" class="stat-item">
      <div class="stat-num">{{ stat.number }}</div>
      <div class="stat-label">{{ stat.label }}</div>
    </div>
  </div>
</template>

<script setup>
import { stats } from "../data/stats";
</script>

<style scoped>
.stats-strip {
  display: flex;
  justify-content: center;
  gap: 5rem;
  padding: 3.5rem 2rem;
  border-bottom: 1px solid var(--cream3);
  flex-wrap: wrap;
}

.stat-num {
  font-family: var(--serif);
  font-size: 2.6rem;
  font-weight: 300;
  color: var(--gold);
  line-height: 1;
  margin-bottom: 0.3rem;
}

.stat-label {
  font-family: var(--sans);
  font-size: 0.6rem;
  letter-spacing: 0.18em;
  text-transform: uppercase;
  color: var(--ink4);
}
</style>
