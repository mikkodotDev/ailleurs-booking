<template>
  <nav :class="{ scrolled: isScrolled }" class="nav-element">
    <div class="nav-logo">Ailleurs</div>
    <ul class="nav-links">
      <li><a href="#destinations">Destinations</a></li>
      <li><a href="#journeys">Journeys</a></li>
      <li><a href="#experiences">Experiences</a></li>
      <li><a href="#about">About</a></li>
    </ul>
    <button class="nav-book">Plan your journey</button>
  </nav>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from "vue";

const isScrolled = ref(false);

const handleScroll = () => {
  isScrolled.value = window.scrollY > 60;
};

onMounted(() => {
  window.addEventListener("scroll", handleScroll);
});

onBeforeUnmount(() => {
  window.removeEventListener("scroll", handleScroll);
});
</script>

<style scoped>
nav.nav-element {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 200;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 1.4rem 3.5rem;
  transition:
    background 0.4s,
    backdrop-filter 0.4s;
}

nav.nav-element.scrolled {
  background: rgba(245, 240, 232, 0.94);
  backdrop-filter: blur(10px);
  border-bottom: 1px solid rgba(201, 185, 154, 0.4);
}

.nav-logo {
  font-family: var(--serif);
  font-size: 1.6rem;
  font-weight: 600;
  letter-spacing: 0.12em;
  color: var(--white);
  text-transform: uppercase;
  transition: color 0.4s;
}

nav.nav-element.scrolled .nav-logo {
  color: var(--ink);
}

.nav-links {
  display: flex;
  gap: 2.5rem;
  list-style: none;
}

.nav-links a {
  font-family: var(--sans);
  font-size: 0.68rem;
  letter-spacing: 0.22em;
  text-transform: uppercase;
  color: rgba(255, 255, 255, 0.8);
  text-decoration: none;
  transition: color 0.2s;
  font-weight: 400;
}

nav.nav-element.scrolled .nav-links a {
  color: var(--ink3);
}

.nav-links a:hover,
nav.nav-element.scrolled .nav-links a:hover {
  color: var(--gold2);
}

.nav-book {
  font-family: var(--sans);
  font-size: 0.65rem;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  font-weight: 600;
  padding: 0.6rem 1.4rem;
  border: 1px solid rgba(255, 255, 255, 0.5);
  color: var(--white);
  background: transparent;
  cursor: pointer;
  transition: all 0.25s;
}

nav.nav-element.scrolled .nav-book {
  border-color: var(--gold);
  color: var(--gold);
}

.nav-book:hover {
  background: var(--gold);
  border-color: var(--gold);
  color: var(--ink);
}

@media (max-width: 700px) {
  nav.nav-element {
    padding: 1rem 1.5rem;
  }

  .nav-links {
    display: none;
  }
}
</style>
