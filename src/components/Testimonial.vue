<template>
  <div class="testi-strip">
    <p class="tq">
      "Ailleurs didn't give us a holiday. They gave us a story we'll spend the
      rest of our lives telling."
    </p>
    <div class="ta">
      — Margot & Luca Ferretti, Milan · Silk Road Journey, 2025
    </div>
  </div>
</template>

<script setup></script>

<style scoped>
.testi-strip {
  background: var(--gold);
  padding: 4.5rem 3.5rem;
  text-align: center;
  position: relative;
  overflow: hidden;
}

.testi-strip::before {
  content: '"';
  position: absolute;
  font-family: var(--serif);
  font-size: 28rem;
  font-weight: 300;
  color: rgba(28, 21, 16, 0.06);
  top: -5rem;
  left: 50%;
  transform: translateX(-50%);
  line-height: 1;
  pointer-events: none;
}

.tq {
  font-family: var(--serif);
  font-style: italic;
  font-size: clamp(1.4rem, 3vw, 2.2rem);
  font-weight: 300;
  color: var(--ink);
  line-height: 1.45;
  max-width: 820px;
  margin: 0 auto 1.6rem;
  position: relative;
  z-index: 1;
}

.ta {
  font-family: var(--sans);
  font-size: 0.65rem;
  letter-spacing: 0.22em;
  text-transform: uppercase;
  color: rgba(28, 21, 16, 0.6);
  position: relative;
  z-index: 1;
}

@media (max-width: 700px) {
  .testi-strip {
    padding: 3rem 1.5rem;
  }
}
</style>
