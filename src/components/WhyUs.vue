<template>
  <section class="sec" id="about" style="text-align: center">
    <div class="s-label-center">Why Ailleurs</div>
    <h2 class="s-title">Travel crafted to a <em>different standard</em></h2>
    <div class="why-grid">
      <div v-for="card in whyUsCards" :key="card.id" class="why-card">
        <div class="why-icon">
          <component :is="iconMap[card.icon]" size="48" stroke-width="1.5" />
        </div>
        <div class="why-title">{{ card.title }}</div>
        <div class="why-desc">{{ card.description }}</div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { whyUsCards } from "../data/whyUs";
import { Compass, Sparkles, Users, Leaf } from "lucide-vue-next";

const iconMap = {
  Compass,
  Sparkles,
  Users,
  Leaf,
};
</script>

<style scoped>
.sec {
  padding: 6rem 3.5rem;
}

.s-label-center {
  font-family: var(--sans);
  font-size: 0.6rem;
  letter-spacing: 0.3em;
  text-transform: uppercase;
  color: var(--gold);
  margin-bottom: 0.7rem;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.7rem;
}

.s-title {
  font-family: var(--serif);
  font-size: clamp(2.2rem, 4vw, 3.4rem);
  font-weight: 300;
  line-height: 1.1;
  letter-spacing: -0.01em;
  color: var(--ink);
}

.s-title em {
  font-style: italic;
  color: var(--gold);
}

.why-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 2.5rem;
  max-width: 1100px;
  margin: 2.5rem auto 0;
}

.why-card {
  text-align: center;
}

.why-icon {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 1rem;
  color: var(--gold);
}

.why-icon :deep(svg) {
  width: 48px;
  height: 48px;
}

.why-title {
  font-family: var(--serif);
  font-size: 1.15rem;
  font-weight: 500;
  color: var(--ink);
  margin-bottom: 0.5rem;
}

.why-desc {
  font-family: var(--sans);
  font-size: 0.75rem;
  color: var(--ink3);
  line-height: 1.75;
  letter-spacing: 0.03em;
}

@media (max-width: 1100px) {
  .why-grid {
    grid-template-columns: 1fr 1fr;
  }
}

@media (max-width: 700px) {
  .sec {
    padding: 4rem 1.5rem;
  }

  .why-grid {
    grid-template-columns: 1fr 1fr;
  }
}
</style>
