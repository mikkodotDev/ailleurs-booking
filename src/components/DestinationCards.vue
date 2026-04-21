<template>
  <section class="sec" id="destinations">
    <div class="dest-header">
      <div>
        <div class="s-label">Explore</div>
        <h2 class="s-title">Where will you go <em>next?</em></h2>
      </div>
      <div class="filter-tabs">
        <button
          v-for="filter in filterOptions"
          :key="filter.value"
          class="ftab"
          :class="{ active: activeFilter === filter.value }"
          @click="activeFilter = filter.value"
        >
          {{ filter.label }}
        </button>
      </div>
    </div>

    <div class="cards-grid">
      <div v-for="dest in filteredDestinations" :key="dest.id" class="dc">
        <img :src="dest.image" :alt="dest.name" class="dc-img" />
        <button class="dc-fav">♡</button>
        <button class="dc-btn">Quick view</button>
        <div class="dc-content">
          <div class="dc-region">{{ dest.region }} · {{ dest.continent }}</div>
          <div class="dc-rating">★★★★★ &nbsp;{{ dest.rating }}</div>
          <div class="dc-name">{{ dest.name }}</div>
          <div class="dc-meta">
            <div class="dc-price">
              from <strong>{{ dest.price }}</strong>
            </div>
            <div class="dc-tag">{{ dest.duration }}</div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, computed } from "vue";
import { destinations, filterOptions } from "../data/destinations";

const activeFilter = ref("all");

const filteredDestinations = computed(() => {
  if (activeFilter.value === "all") {
    return destinations;
  }
  return destinations.filter((dest) => dest.continent === activeFilter.value);
});
</script>

<style scoped>
.sec {
  padding: 6rem 3.5rem;
}

.dest-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  margin-bottom: 3rem;
  gap: 2rem;
  flex-wrap: wrap;
}

.s-label {
  font-family: var(--sans);
  font-size: 0.6rem;
  letter-spacing: 0.3em;
  text-transform: uppercase;
  color: var(--gold);
  margin-bottom: 0.7rem;
  display: flex;
  align-items: center;
  gap: 0.7rem;
}

.s-label::after {
  content: "";
  flex: 1;
  max-width: 60px;
  height: 1px;
  background: var(--gold);
  opacity: 0.5;
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

.filter-tabs {
  display: flex;
  border: 1px solid var(--cream3);
  overflow: hidden;
}

.ftab {
  font-family: var(--sans);
  font-size: 0.62rem;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  padding: 0.55rem 1.1rem;
  background: transparent;
  border: none;
  border-right: 1px solid var(--cream3);
  cursor: pointer;
  color: var(--ink3);
  transition: all 0.2s;
  font-weight: 400;
}

.ftab:last-child {
  border-right: none;
}

.ftab:hover {
  background: var(--cream2);
  color: var(--ink);
}

.ftab.active {
  background: var(--gold);
  color: var(--ink);
}

.cards-grid {
  display: grid;
  grid-template-columns: repeat(12, 1fr);
  gap: 1.2rem;
}

.dc {
  position: relative;
  overflow: hidden;
  cursor: pointer;
  background: var(--ink2);
}

.dc:nth-child(1) {
  grid-column: 1/6;
  aspect-ratio: 4/5;
}

.dc:nth-child(2) {
  grid-column: 6/9;
  aspect-ratio: 3/5;
}

.dc:nth-child(3) {
  grid-column: 9/13;
  aspect-ratio: 4/5;
}

.dc:nth-child(4) {
  grid-column: 1/5;
  grid-row: 2;
  aspect-ratio: 16/9;
}

.dc:nth-child(5) {
  grid-column: 5/9;
  grid-row: 2;
  aspect-ratio: 16/9;
}

.dc:nth-child(6) {
  grid-column: 9/13;
  grid-row: 2;
  aspect-ratio: 16/9;
}

.dc-img {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center;
  transition: transform 0.7s cubic-bezier(0.25, 0.46, 0.45, 0.94);
}

.dc:hover .dc-img {
  transform: scale(1.07);
}

.dc::after {
  content: "";
  position: absolute;
  inset: 0;
  background: linear-gradient(
    to top,
    rgba(28, 21, 16, 0.9) 0%,
    rgba(28, 21, 16, 0.3) 40%,
    rgba(28, 21, 16, 0.05) 100%
  );
  transition: opacity 0.4s;
}

.dc:hover::after {
  background: linear-gradient(
    to top,
    rgba(28, 21, 16, 0.95) 0%,
    rgba(28, 21, 16, 0.45) 55%,
    rgba(28, 21, 16, 0.1) 100%
  );
}

.dc-content {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  padding: 1.6rem;
  z-index: 2;
  transform: translateY(0);
  transition: transform 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
}

.dc:hover .dc-content {
  transform: translateY(-6px);
}

.dc-region {
  font-family: var(--sans);
  font-size: 0.55rem;
  letter-spacing: 0.25em;
  text-transform: uppercase;
  color: var(--gold2);
  margin-bottom: 0.35rem;
  display: flex;
  align-items: center;
  gap: 0.4rem;
}

.dc-region::before {
  content: "";
  display: inline-block;
  width: 14px;
  height: 1px;
  background: var(--gold2);
}

.dc-rating {
  font-family: var(--sans);
  font-size: 0.6rem;
  color: var(--gold2);
  margin-bottom: 0.35rem;
  letter-spacing: 0.05em;
}

.dc-name {
  font-family: var(--serif);
  font-size: 1.6rem;
  font-weight: 300;
  color: var(--white);
  line-height: 1.15;
  margin-bottom: 0.5rem;
  letter-spacing: -0.01em;
}

.dc-meta {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.dc-price {
  font-family: var(--serif);
  font-size: 0.9rem;
  color: rgba(245, 240, 232, 0.7);
}

.dc-price strong {
  font-size: 1.3rem;
  font-weight: 500;
  color: var(--white);
}

.dc-tag {
  font-family: var(--sans);
  font-size: 0.55rem;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  padding: 0.25rem 0.65rem;
  border: 1px solid rgba(184, 145, 58, 0.5);
  color: var(--gold2);
}

.dc-btn {
  position: absolute;
  top: 1.2rem;
  right: 1.2rem;
  z-index: 3;
  font-family: var(--sans);
  font-size: 0.58rem;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  padding: 0.45rem 0.9rem;
  background: rgba(245, 240, 232, 0.9);
  color: var(--ink);
  border: none;
  cursor: pointer;
  opacity: 0;
  transform: translateY(-6px);
  transition:
    opacity 0.3s,
    transform 0.3s;
  font-weight: 600;
}

.dc:hover .dc-btn {
  opacity: 1;
  transform: translateY(0);
}

.dc-btn:hover {
  background: var(--gold);
}

.dc-fav {
  position: absolute;
  top: 1.2rem;
  left: 1.2rem;
  z-index: 3;
  width: 32px;
  height: 32px;
  background: rgba(28, 21, 16, 0.5);
  border: 1px solid rgba(245, 240, 232, 0.2);
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  font-size: 0.75rem;
  opacity: 0;
  transform: scale(0.8);
  transition: all 0.25s;
  color: var(--white);
}

.dc:hover .dc-fav {
  opacity: 1;
  transform: scale(1);
}

.dc-fav:hover {
  background: rgba(184, 145, 58, 0.6);
}

@media (max-width: 1100px) {
  .cards-grid {
    grid-template-columns: repeat(6, 1fr);
  }

  .dc:nth-child(1) {
    grid-column: 1/4;
    grid-row: 1;
  }

  .dc:nth-child(2) {
    grid-column: 4/7;
    grid-row: 1;
  }

  .dc:nth-child(3) {
    grid-column: 1/4;
    grid-row: 2;
  }

  .dc:nth-child(4) {
    grid-column: 4/7;
    grid-row: 2;
  }

  .dc:nth-child(5) {
    grid-column: 1/4;
    grid-row: 3;
  }

  .dc:nth-child(6) {
    grid-column: 4/7;
    grid-row: 3;
  }

  .dc {
    aspect-ratio: 4/3 !important;
  }
}

@media (max-width: 700px) {
  .sec {
    padding: 4rem 1.5rem;
  }

  .cards-grid {
    grid-template-columns: 1fr;
  }

  .dc {
    grid-column: 1/-1 !important;
    grid-row: auto !important;
    aspect-ratio: 4/3 !important;
  }
}
</style>
