<template>
  <section class="hero">
    <div class="hero-bg"></div>
    <div class="hero-mountains">
      <svg
        viewBox="0 0 1440 200"
        preserveAspectRatio="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M0,200 L0,140 L120,80 L240,120 L360,60 L480,100 L540,40 L600,80 L720,20 L800,70 L900,30 L1000,90 L1100,50 L1200,100 L1320,60 L1440,110 L1440,200 Z"
          fill="rgba(28,21,16,0.5)"
        />
        <path
          d="M0,200 L0,160 L180,110 L300,140 L420,90 L560,120 L680,70 L760,100 L880,60 L960,90 L1080,70 L1200,120 L1360,80 L1440,130 L1440,200 Z"
          fill="rgba(28,21,16,0.35)"
        />
      </svg>
    </div>
    <div class="hero-content">
      <div class="hero-label">Curated travel · Est. 2012</div>
      <h1 class="hero-title">Go <em>somewhere</em><br />that changes you</h1>
      <p class="hero-sub">
        Handcrafted journeys to 140 destinations across six continents. We don't
        book trips — we architect experiences that last a lifetime.
      </p>
      <div class="hero-actions">
        <button class="btn-gold">Explore destinations</button>
        <button class="btn-ghost-w">View our stories</button>
      </div>
    </div>
    <div class="hero-scroll">
      <div class="hero-scroll-label">Scroll</div>
      <div class="hero-scroll-line"></div>
    </div>
  </section>
</template>

<script setup></script>

<style scoped>
.hero {
  height: 100vh;
  min-height: 700px;
  position: relative;
  display: flex;
  align-items: flex-end;
  overflow: hidden;
}

.hero-bg {
  position: absolute;
  inset: 0;
  background:
    linear-gradient(
      to bottom,
      rgba(28, 21, 16, 0.25) 0%,
      rgba(28, 21, 16, 0.05) 35%,
      rgba(28, 21, 16, 0.7) 100%
    ),
    linear-gradient(
      135deg,
      #2c4a3e 0%,
      #3d6b5a 18%,
      #7a9e7e 38%,
      #c4a882 58%,
      #8b6914 78%,
      #5c3d11 100%
    );
  background-size: cover;
}

.hero-bg::after {
  content: "";
  position: absolute;
  inset: 0;
  background-image: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Ccircle cx='30' cy='30' r='1' fill='%23ffffff' fill-opacity='0.025'/%3E%3C/svg%3E");
}

.hero-mountains {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  height: 55%;
  pointer-events: none;
}

.hero-mountains svg {
  width: 100%;
  height: 100%;
}

.hero-content {
  position: relative;
  z-index: 2;
  padding: 0 3.5rem 5.5rem;
  max-width: 800px;
  animation: heroIn 1.2s cubic-bezier(0.16, 1, 0.3, 1) both;
}

@keyframes heroIn {
  from {
    opacity: 0;
    transform: translateY(28px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.hero-label {
  font-family: var(--sans);
  font-size: 0.65rem;
  letter-spacing: 0.35em;
  text-transform: uppercase;
  color: var(--gold2);
  margin-bottom: 1.2rem;
  display: flex;
  align-items: center;
  gap: 0.8rem;
  animation: heroIn 1.2s 0.1s cubic-bezier(0.16, 1, 0.3, 1) both;
}

.hero-label::before {
  content: "";
  display: inline-block;
  width: 36px;
  height: 1px;
  background: var(--gold2);
}

.hero-title {
  font-family: var(--serif);
  font-size: clamp(3.2rem, 8vw, 7rem);
  font-weight: 300;
  line-height: 0.95;
  letter-spacing: -0.01em;
  color: var(--white);
  margin-bottom: 1.4rem;
  animation: heroIn 1.2s 0.2s cubic-bezier(0.16, 1, 0.3, 1) both;
}

.hero-title em {
  font-style: italic;
  color: var(--gold-lt);
}

.hero-sub {
  font-family: var(--sans);
  font-size: 0.82rem;
  letter-spacing: 0.1em;
  color: rgba(245, 240, 232, 0.7);
  max-width: 420px;
  line-height: 1.9;
  margin-bottom: 2.4rem;
  animation: heroIn 1.2s 0.3s cubic-bezier(0.16, 1, 0.3, 1) both;
}

.hero-actions {
  display: flex;
  gap: 1rem;
  align-items: center;
  flex-wrap: wrap;
  animation: heroIn 1.2s 0.4s cubic-bezier(0.16, 1, 0.3, 1) both;
}

.btn-gold {
  font-family: var(--sans);
  font-size: 0.68rem;
  letter-spacing: 0.22em;
  text-transform: uppercase;
  font-weight: 600;
  padding: 0.95rem 2.2rem;
  background: var(--gold);
  color: var(--ink);
  border: none;
  cursor: pointer;
  transition: all 0.25s;
  position: relative;
  overflow: hidden;
}

.btn-gold::after {
  content: "";
  position: absolute;
  inset: 0;
  background: linear-gradient(
    90deg,
    transparent,
    rgba(255, 255, 255, 0.25),
    transparent
  );
  transform: translateX(-100%);
  transition: transform 0.5s;
}

.btn-gold:hover::after {
  transform: translateX(100%);
}

.btn-gold:hover {
  background: var(--gold2);
  box-shadow: 0 8px 30px rgba(184, 145, 58, 0.4);
}

.btn-ghost-w {
  font-family: var(--sans);
  font-size: 0.65rem;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  padding: 0.9rem 1.8rem;
  border: 1px solid rgba(255, 255, 255, 0.4);
  color: var(--white);
  background: transparent;
  cursor: pointer;
  transition: all 0.2s;
}

.btn-ghost-w:hover {
  background: rgba(255, 255, 255, 0.1);
  border-color: rgba(255, 255, 255, 0.7);
}

.hero-scroll {
  position: absolute;
  bottom: 2.5rem;
  right: 3.5rem;
  z-index: 2;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.5rem;
  animation: heroIn 1.2s 0.6s cubic-bezier(0.16, 1, 0.3, 1) both;
}

.hero-scroll-label {
  font-family: var(--sans);
  font-size: 0.55rem;
  letter-spacing: 0.3em;
  text-transform: uppercase;
  color: rgba(255, 255, 255, 0.5);
  writing-mode: vertical-rl;
}

.hero-scroll-line {
  width: 1px;
  height: 60px;
  background: linear-gradient(to bottom, rgba(255, 255, 255, 0.5), transparent);
  animation: scrollPulse 2s ease-in-out infinite;
}

@keyframes scrollPulse {
  0%,
  100% {
    opacity: 0.5;
  }
  50% {
    opacity: 1;
  }
}

@media (max-width: 700px) {
  .hero-content {
    padding: 0 1.5rem 4rem;
  }

  .hero-scroll {
    display: none;
  }
}
</style>
