<template>
  <section class="sec" id="experiences" style="background: var(--cream2)">
    <div style="margin-bottom: 3rem">
      <div class="s-label">Curated experiences</div>
      <h2 class="s-title">Beyond the <em>itinerary</em></h2>
      <p class="s-sub">
        Each journey includes handpicked experiences you won't find on any
        booking platform.
      </p>
    </div>
    <div class="exp-grid">
      <div v-for="exp in experiences" :key="exp.id" class="exp-card">
        <div class="exp-img">
          <img :src="exp.image" :alt="exp.name" class="exp-img-bg" />
          <div class="exp-etag">{{ exp.category }}</div>
        </div>
        <div class="exp-body">
          <div class="exp-name">{{ exp.name }}</div>
          <div class="exp-loc">{{ exp.location }}</div>
          <div class="exp-desc">{{ exp.description }}</div>
          <div class="exp-footer">
            <div>
              <div class="exp-price">{{ exp.price }}</div>
              <div class="exp-dur">{{ exp.duration }}</div>
            </div>
            <button class="exp-btn" @click="openBooking(exp)">Book now</button>
          </div>
        </div>
      </div>
    </div>

    <!-- Booking Modal -->
    <div v-if="showModal" class="modal-overlay" @click.self="closeModal">
      <div class="modal-content">
        <div class="modal-header">
          <div>
            <div class="modal-label">Book your experience</div>
            <h3 class="modal-title">{{ selectedExperience?.name }}</h3>
          </div>
          <button class="modal-close" @click="closeModal">✕</button>
        </div>

        <form @submit.prevent="submitForm" class="booking-form">
          <div class="form-group">
            <label for="name">Full Name</label>
            <input
              id="name"
              v-model="formData.name"
              type="text"
              placeholder="Your name"
              required
            />
          </div>

          <div class="form-group">
            <label for="email">Email Address</label>
            <input
              id="email"
              v-model="formData.email"
              type="email"
              placeholder="your.email@example.com"
              required
            />
          </div>

          <div class="form-row">
            <div class="form-group">
              <label for="date">Preferred Date</label>
              <input
                id="date"
                v-model="formData.date"
                type="date"
                required
              />
            </div>
            <div class="form-group">
              <label for="travelers">Number of Travelers</label>
              <input
                id="travelers"
                v-model.number="formData.travelers"
                type="number"
                min="1"
                max="10"
                required
              />
            </div>
          </div>

          <div class="form-group">
            <label for="requests">Special Requests</label>
            <textarea
              id="requests"
              v-model="formData.requests"
              placeholder="Any special requests or dietary restrictions..."
              rows="4"
            ></textarea>
          </div>

          <div class="form-footer">
            <button type="button" class="btn-cancel" @click="closeModal">
              Cancel
            </button>
            <button type="submit" class="btn-submit">Confirm booking</button>
          </div>
        </form>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";
import { experiences } from "../data/experiences";

const showModal = ref(false);
const selectedExperience = ref(null);
const formData = ref({
  name: "",
  email: "",
  date: "",
  travelers: 1,
  requests: "",
});

const openBooking = (experience) => {
  selectedExperience.value = experience;
  showModal.value = true;
  document.body.style.overflow = "hidden";
};

const closeModal = () => {
  showModal.value = false;
  document.body.style.overflow = "auto";
  formData.value = {
    name: "",
    email: "",
    date: "",
    travelers: 1,
    requests: "",
  };
};

const submitForm = () => {
  console.log("Booking submitted:", {
    experience: selectedExperience.value?.name,
    ...formData.value,
  });
  alert(`Booking request submitted for ${selectedExperience.value?.name}!`);
  closeModal();
};
</script>

<style scoped>
.sec {
  padding: 6rem 3.5rem;
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

.s-sub {
  font-family: var(--sans);
  font-size: 0.78rem;
  letter-spacing: 0.06em;
  color: var(--ink3);
  max-width: 500px;
  line-height: 1.85;
  margin-top: 0.8rem;
}

.exp-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 1.5rem;
}

.exp-card {
  background: var(--white);
  overflow: hidden;
  transition:
    transform 0.3s,
    box-shadow 0.3s;
  cursor: pointer;
}

.exp-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 16px 48px rgba(28, 21, 16, 0.12);
}

.exp-img {
  height: 180px;
  position: relative;
  overflow: hidden;
}

.exp-img-bg {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center;
  transition: transform 0.5s;
}

.exp-card:hover .exp-img-bg {
  transform: scale(1.06);
}

.exp-etag {
  position: absolute;
  top: 0.8rem;
  left: 0.8rem;
  font-family: var(--sans);
  font-size: 0.55rem;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  padding: 0.25rem 0.6rem;
  background: var(--gold);
  color: var(--ink);
  font-weight: 600;
  z-index: 2;
}

.exp-body {
  padding: 1.4rem;
}

.exp-name {
  font-family: var(--serif);
  font-size: 1.15rem;
  font-weight: 500;
  color: var(--ink);
  margin-bottom: 0.4rem;
  line-height: 1.25;
}

.exp-loc {
  font-family: var(--sans);
  font-size: 0.62rem;
  letter-spacing: 0.1em;
  color: var(--ink4);
  text-transform: uppercase;
  margin-bottom: 0.7rem;
}

.exp-desc {
  font-size: 0.78rem;
  color: var(--ink3);
  line-height: 1.7;
  margin-bottom: 1rem;
  letter-spacing: 0.02em;
}

.exp-footer {
  display: flex;
  align-items: center;
  justify-content: space-between;
  border-top: 1px solid var(--cream3);
  padding-top: 0.9rem;
}

.exp-price {
  font-family: var(--serif);
  font-size: 1.2rem;
  font-weight: 500;
  color: var(--gold);
}

.exp-dur {
  font-family: var(--sans);
  font-size: 0.58rem;
  letter-spacing: 0.1em;
  color: var(--ink4);
  text-transform: uppercase;
}

.exp-btn {
  font-family: var(--sans);
  font-size: 0.58rem;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  font-weight: 600;
  padding: 0.45rem 0.9rem;
  background: transparent;
  border: 1px solid var(--cream3);
  color: var(--ink3);
  cursor: pointer;
  transition: all 0.2s;
}

.exp-btn:hover {
  border-color: var(--gold);
  color: var(--gold);
}

@media (max-width: 1100px) {
  .exp-grid {
    grid-template-columns: 1fr 1fr;
  }
}

@media (max-width: 700px) {
  .sec {
    padding: 4rem 1.5rem;
  }

  .exp-grid {
    grid-template-columns: 1fr;
  }
}

/* Modal Styles */
.modal-overlay {
  position: fixed;
  inset: 0;
  background: rgba(28, 21, 16, 0.6);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1000;
  padding: 1rem;
  backdrop-filter: blur(4px);
  animation: fadeIn 0.3s ease-out;
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

.modal-content {
  background: var(--white);
  border-radius: 8px;
  max-width: 500px;
  width: 100%;
  box-shadow: 0 20px 60px rgba(28, 21, 16, 0.15);
  animation: slideUp 0.3s ease-out;
}

@keyframes slideUp {
  from {
    transform: translateY(20px);
    opacity: 0;
  }
  to {
    transform: translateY(0);
    opacity: 1;
  }
}

.modal-header {
  padding: 2rem;
  border-bottom: 2px solid var(--cream2);
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
}

.modal-label {
  font-family: var(--sans);
  font-size: 0.6rem;
  letter-spacing: 0.3em;
  text-transform: uppercase;
  color: var(--gold);
  margin-bottom: 0.5rem;
}

.modal-title {
  font-family: var(--serif);
  font-size: 1.8rem;
  font-weight: 300;
  color: var(--ink);
  line-height: 1.2;
}

.modal-close {
  background: none;
  border: none;
  font-size: 1.5rem;
  color: var(--ink3);
  cursor: pointer;
  transition: color 0.2s;
  padding: 0;
  width: 32px;
  height: 32px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.modal-close:hover {
  color: var(--gold);
}

.booking-form {
  padding: 2rem;
}

.form-group {
  margin-bottom: 1.5rem;
}

.form-row {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1rem;
}

.form-group label {
  display: block;
  font-family: var(--sans);
  font-size: 0.75rem;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--ink);
  margin-bottom: 0.5rem;
  font-weight: 500;
}

.form-group input,
.form-group textarea {
  width: 100%;
  padding: 0.75rem;
  border: 1px solid var(--cream3);
  border-radius: 4px;
  font-family: var(--sans);
  font-size: 0.9rem;
  color: var(--ink);
  transition: border-color 0.2s, box-shadow 0.2s;
}

.form-group input:focus,
.form-group textarea:focus {
  outline: none;
  border-color: var(--gold);
  box-shadow: 0 0 0 3px rgba(184, 145, 58, 0.1);
}

.form-group textarea {
  resize: vertical;
  font-family: var(--sans);
}

.form-footer {
  display: flex;
  gap: 1rem;
  margin-top: 2rem;
  padding-top: 1.5rem;
  border-top: 1px solid var(--cream2);
}

.btn-cancel,
.btn-submit {
  flex: 1;
  padding: 0.85rem 1.5rem;
  font-family: var(--sans);
  font-size: 0.75rem;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  font-weight: 600;
  border-radius: 4px;
  cursor: pointer;
  transition: all 0.2s;
  border: none;
}

.btn-cancel {
  background: var(--cream2);
  color: var(--ink);
  border: 1px solid var(--cream3);
}

.btn-cancel:hover {
  background: var(--cream3);
  border-color: var(--ink3);
}

.btn-submit {
  background: var(--gold);
  color: var(--ink);
  font-weight: 700;
}

.btn-submit:hover {
  background: var(--gold2);
  box-shadow: 0 8px 20px rgba(184, 145, 58, 0.3);
  transform: translateY(-2px);
}

.btn-submit:active {
  transform: translateY(0);
}
</style>
