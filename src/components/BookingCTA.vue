<template>
  <section class="booking-cta">
    <div class="bk-pat"></div>
    <div class="bk-glow"></div>
    <div class="bk-inner">
      <div>
        <div class="bk-label">Start planning</div>
        <h2 class="bk-title">Your next chapter<br>begins <em>here</em></h2>
        <p class="bk-sub">Tell us where you dream of going and our journey architects will craft a bespoke itinerary within 48 hours. No commitment, no cost — just possibility.</p>
      </div>
      <div class="bk-form">
        <div class="bk-form-title">Request a bespoke journey</div>
        <div class="ff">
          <label class="fl">Your name</label>
          <input v-model="formData.name" class="fi" type="text" placeholder="Full name">
        </div>
        <div class="ff">
          <label class="fl">Email</label>
          <input v-model="formData.email" class="fi" type="email" placeholder="your@email.com">
        </div>
        <div class="fr">
          <div class="ff">
            <label class="fl">Destination</label>
            <select v-model="formData.destination" class="fi">
              <option value="">Any dream</option>
              <option>Japan</option>
              <option>Italy</option>
              <option>Patagonia</option>
              <option>Morocco</option>
              <option>Greece</option>
              <option>Bali</option>
              <option>Silk Road</option>
            </select>
          </div>
          <div class="ff">
            <label class="fl">Budget pp</label>
            <select v-model="formData.budget" class="fi">
              <option>$2k – $5k</option>
              <option>$5k – $10k</option>
              <option>$10k – $20k</option>
              <option>$20k+</option>
            </select>
          </div>
        </div>
        <div class="ff">
          <label class="fl">When are you thinking?</label>
          <input v-model="formData.timing" class="fi" type="text" placeholder="e.g. Spring 2027, flexible">
        </div>
        <button class="fs" @click="handleSubmit">Request my itinerary →</button>
        <div class="ffine">We respond within 48 hours · No booking required</div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const formData = ref({
  name: '',
  email: '',
  destination: '',
  budget: '$2k – $5k',
  timing: ''
})

const handleSubmit = () => {
  if (!formData.value.name || !formData.value.email || !formData.value.destination) {
    alert('Please fill in all required fields')
    return
  }
  console.log('Form submitted:', formData.value)
  alert('Thank you! We will respond within 48 hours.')
  // Reset form
  formData.value = {
    name: '',
    email: '',
    destination: '',
    budget: '$2k – $5k',
    timing: ''
  }
}
</script>

<style scoped>
.booking-cta {
  background: var(--ink);
  padding: 7rem 3.5rem;
  position: relative;
  overflow: hidden;
}

.bk-pat {
  position: absolute;
  inset: 0;
  background-image: linear-gradient(rgba(201, 185, 154, 0.04) 1px, transparent 1px),
    linear-gradient(90deg, rgba(201, 185, 154, 0.04) 1px, transparent 1px);
  background-size: 80px 80px;
}

.bk-glow {
  position: absolute;
  width: 800px;
  height: 400px;
  border-radius: 50%;
  background: radial-gradient(ellipse, rgba(184, 145, 58, 0.08), transparent 70%);
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.bk-inner {
  position: relative;
  z-index: 2;
  display: grid;
  grid-template-columns: 1fr auto;
  gap: 4rem;
  align-items: center;
  max-width: 1100px;
  margin: 0 auto;
}

.bk-label {
  font-family: var(--sans);
  font-size: 0.6rem;
  letter-spacing: 0.3em;
  text-transform: uppercase;
  color: var(--gold);
  margin-bottom: 1rem;
  display: flex;
  align-items: center;
  gap: 0.6rem;
}

.bk-label::before {
  content: '';
  width: 24px;
  height: 1px;
  background: var(--gold);
}

.bk-title {
  font-family: var(--serif);
  font-size: clamp(2.2rem, 4vw, 3.8rem);
  font-weight: 300;
  color: var(--white);
  line-height: 1.1;
  margin-bottom: 1rem;
}

.bk-title em {
  font-style: italic;
  color: var(--gold-lt);
}

.bk-sub {
  font-family: var(--sans);
  font-size: 0.78rem;
  color: rgba(245, 240, 232, 0.5);
  line-height: 1.8;
  letter-spacing: 0.04em;
  max-width: 480px;
}

.bk-form {
  min-width: 340px;
  background: rgba(245, 240, 232, 0.05);
  border: 1px solid rgba(201, 185, 154, 0.15);
  padding: 2.2rem;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.bk-form-title {
  font-family: var(--serif);
  font-size: 1.1rem;
  color: var(--white);
  font-weight: 300;
  margin-bottom: 0.5rem;
  padding-bottom: 1rem;
  border-bottom: 1px solid rgba(201, 185, 154, 0.15);
}

.ff {
  display: flex;
  flex-direction: column;
  gap: 0.35rem;
}

.fl {
  font-family: var(--sans);
  font-size: 0.55rem;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: var(--ink4);
  font-weight: 600;
}

.fi {
  padding: 0.75rem 0.9rem;
  background: rgba(245, 240, 232, 0.05);
  border: 1px solid rgba(201, 185, 154, 0.2);
  color: var(--white);
  font-family: var(--serif);
  font-size: 0.95rem;
  outline: none;
  transition: border-color 0.2s;
  width: 100%;
  appearance: none;
  -webkit-appearance: none;
}

.fi:focus {
  border-color: rgba(184, 145, 58, 0.5);
}

.fi::placeholder {
  color: rgba(245, 240, 232, 0.3);
  font-style: italic;
}

.fi option {
  background: var(--ink2);
}

.fr {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 0.8rem;
}

.fs {
  font-family: var(--sans);
  font-size: 0.68rem;
  letter-spacing: 0.22em;
  text-transform: uppercase;
  font-weight: 600;
  padding: 1rem;
  background: var(--gold);
  color: var(--ink);
  border: none;
  cursor: pointer;
  transition: all 0.25s;
  margin-top: 0.5rem;
}

.fs:hover {
  background: var(--gold2);
  box-shadow: 0 8px 28px rgba(184, 145, 58, 0.3);
}

.ffine {
  font-family: var(--sans);
  font-size: 0.55rem;
  letter-spacing: 0.08em;
  color: rgba(245, 240, 232, 0.3);
  text-align: center;
}

@media (max-width: 1100px) {
  .bk-inner {
    grid-template-columns: 1fr;
  }

  .bk-form {
    min-width: auto;
  }
}

@media (max-width: 700px) {
  .booking-cta {
    padding: 4rem 1.5rem;
  }

  .fr {
    grid-template-columns: 1fr;
  }
}
</style>
