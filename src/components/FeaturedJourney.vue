<template>
  <section class="featured" id="journeys">
    <div class="feat-bg"></div>
    <div class="feat-glow"></div>
    <div class="feat-inner">
      <div>
        <div class="feat-label">Journey of the season</div>
        <h2 class="feat-title">The Silk Road<br /><em>Reimagined</em></h2>
        <p class="feat-desc">
          Seventeen days through Uzbekistan, Georgia, and Armenia — traversing
          ancient trade routes that once connected East and West. Walled cities
          at dusk. Caravanserais turned boutique hotels. Markets unchanged for
          eight centuries.
        </p>
        <div class="feat-details">
          <div class="feat-detail">
            <div class="fdl">Duration</div>
            <div class="fdv">17 days</div>
          </div>
          <div class="feat-detail">
            <div class="fdl">Highlights</div>
            <div class="fdv">Samarkand · Tbilisi · Yerevan</div>
          </div>
          <div class="feat-detail">
            <div class="fdl">Group size</div>
            <div class="fdv">Max 10 travellers</div>
          </div>
          <div class="feat-detail">
            <div class="fdl">Departs</div>
            <div class="fdv">Sept – Nov 2026</div>
          </div>
        </div>
        <div class="feat-price-row">
          <span class="feat-from">From</span>
          <div class="feat-price"><sup>$</sup>6,490</div>
          <span class="feat-pp">per person</span>
        </div>
        <div class="feat-btns">
          <button class="btn-gold">Reserve your place</button>
          <button class="btn-ghost-gold">View full itinerary</button>
        </div>
      </div>
      <div class="feat-visuals">
        <img 
          :src="samarkandImg" 
          alt="Registan Square, Samarkand"
          class="fv-main" 
        />
        <img 
          :src="tbilisiImg" 
          alt="Tbilisi, Georgia"
          class="fv-a1" 
        />
        <img 
          :src="yerevanImg" 
          alt="Yerevan, Armenia"
          class="fv-a2" 
        />
        <div class="feat-badge">
          <div class="fb-top">Only</div>
          <div class="fb-num">4</div>
          <div class="fb-bot">spots left</div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import samarkandImg from "@/assets/images/samarkand.jpg";
import tbilisiImg from "@/assets/images/tbilisi.jpg";
import yerevanImg from "@/assets/images/yerevan.jpg";
</script>

<style scoped>
.featured {
  background: var(--ink);
  color: var(--white);
  padding: 6rem 3.5rem;
  position: relative;
  overflow: hidden;
}

.feat-bg {
  position: absolute;
  inset: 0;
  background: linear-gradient(
    135deg,
    #1c1510,
    #2c1f14 40%,
    #3d2a1a 60%,
    #1c1510
  );
}

.feat-glow {
  position: absolute;
  inset: 0;
  background:
    radial-gradient(
      circle at 20% 50%,
      rgba(184, 145, 58, 0.07),
      transparent 50%
    ),
    radial-gradient(
      circle at 80% 20%,
      rgba(184, 145, 58, 0.05),
      transparent 40%
    );
}

.feat-inner {
  position: relative;
  z-index: 2;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 6rem;
  align-items: center;
  max-width: 1200px;
  margin: 0 auto;
}

.feat-label {
  font-family: var(--sans);
  font-size: 0.6rem;
  letter-spacing: 0.3em;
  text-transform: uppercase;
  color: var(--gold2);
  margin-bottom: 1rem;
  display: flex;
  align-items: center;
  gap: 0.7rem;
}

.feat-label::before {
  content: "";
  width: 30px;
  height: 1px;
  background: var(--gold2);
}

.feat-title {
  font-family: var(--serif);
  font-size: clamp(2.4rem, 4vw, 3.8rem);
  font-weight: 300;
  line-height: 1.1;
  color: var(--white);
  margin-bottom: 1.2rem;
}

.feat-title em {
  font-style: italic;
  color: var(--gold-lt);
}

.feat-desc {
  font-family: var(--sans);
  font-size: 0.8rem;
  color: rgba(245, 240, 232, 0.6);
  line-height: 1.9;
  margin-bottom: 2rem;
  letter-spacing: 0.04em;
}

.feat-details {
  display: flex;
  gap: 2rem;
  margin-bottom: 2.4rem;
  flex-wrap: wrap;
}

.feat-detail {
  padding-left: 1rem;
  border-left: 1px solid rgba(184, 145, 58, 0.3);
}

.fdl {
  font-family: var(--sans);
  font-size: 0.55rem;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: var(--ink4);
}

.fdv {
  font-family: var(--serif);
  font-size: 1rem;
  color: var(--white);
  font-weight: 300;
}

.feat-price-row {
  display: flex;
  align-items: baseline;
  gap: 1rem;
  margin-bottom: 1.6rem;
}

.feat-from {
  font-family: var(--sans);
  font-size: 0.62rem;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: var(--ink4);
}

.feat-price {
  font-family: var(--serif);
  font-size: 2.8rem;
  font-weight: 300;
  color: var(--gold-lt);
  line-height: 1;
}

.feat-price sup {
  font-size: 1.2rem;
  vertical-align: top;
  margin-top: 0.5rem;
  display: inline-block;
}

.feat-pp {
  font-family: var(--sans);
  font-size: 0.62rem;
  color: var(--ink4);
  letter-spacing: 0.08em;
  align-self: flex-end;
  padding-bottom: 0.3rem;
}

.feat-btns {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
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

.btn-ghost-gold {
  font-family: var(--sans);
  font-size: 0.65rem;
  letter-spacing: 0.18em;
  text-transform: uppercase;
  background: transparent;
  border: 1px solid rgba(201, 185, 154, 0.25);
  color: rgba(245, 240, 232, 0.6);
  padding: 0.9rem 1.6rem;
  cursor: pointer;
  transition: all 0.2s;
}

.btn-ghost-gold:hover {
  border-color: rgba(201, 185, 154, 0.6);
  color: rgba(245, 240, 232, 0.9);
}

.feat-visuals {
  position: relative;
  height: 520px;
}

.fv-main {
  position: absolute;
  top: 0;
  left: 0;
  width: 75%;
  height: 80%;
  object-fit: cover;
  object-position: center;
  overflow: hidden;
}

.fv-main::before {
  content: "";
  position: absolute;
  inset: 0;
  background: transparent;
}

.fv-a1 {
  position: absolute;
  bottom: 0;
  right: 0;
  width: 48%;
  height: 50%;
  object-fit: cover;
  object-position: center;
  border: 3px solid var(--ink);
}

.fv-a2 {
  position: absolute;
  top: 45%;
  left: 58%;
  width: 30%;
  height: 28%;
  object-fit: cover;
  object-position: center;
  border: 3px solid var(--ink);
}

.feat-badge {
  position: absolute;
  top: -1.2rem;
  right: 25%;
  width: 80px;
  height: 80px;
  border-radius: 50%;
  background: var(--gold);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  z-index: 5;
  border: 3px solid var(--ink);
}

.fb-top {
  font-family: var(--sans);
  font-size: 0.45rem;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: var(--ink);
  font-weight: 600;
}

.fb-num {
  font-family: var(--serif);
  font-size: 1.4rem;
  font-weight: 600;
  color: var(--ink);
  line-height: 1;
}

.fb-bot {
  font-family: var(--sans);
  font-size: 0.42rem;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--ink2);
}

@media (max-width: 1100px) {
  .feat-inner {
    grid-template-columns: 1fr;
    gap: 3rem;
  }

  .feat-visuals {
    height: 320px;
  }
}

@media (max-width: 700px) {
  .feat-visuals {
    height: 220px;
  }
}
</style>
