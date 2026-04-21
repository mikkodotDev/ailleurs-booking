<template>
  <div class="search-bar">
    <div class="search-field">
      <div class="sf-label">Destination</div>
      <div class="sf-val">Where do you want to go?</div>
    </div>
    <div class="search-field">
      <div class="sf-label">Travel Dates</div>
      <div class="sf-val">Select dates</div>
    </div>
    <div class="search-field">
      <div class="sf-label">Travellers</div>
      <div class="sf-val">2 adults</div>
    </div>
    <div class="search-field">
      <div class="sf-label">Journey Style</div>
      <div class="sf-val">Any style</div>
    </div>
    <button class="search-btn">Search Journeys</button>
  </div>
</template>

<script setup></script>

<style scoped>
.search-bar {
  background: var(--white);
  margin: 0 3.5rem;
  margin-top: -3rem;
  position: relative;
  z-index: 10;
  box-shadow: 0 20px 60px rgba(28, 21, 16, 0.15);
  display: flex;
  align-items: stretch;
}

.search-field {
  flex: 1;
  padding: 1.4rem 1.8rem;
  border-right: 1px solid var(--cream3);
  display: flex;
  flex-direction: column;
  gap: 0.25rem;
  cursor: pointer;
}

.search-field:last-of-type {
  border-right: none;
}

.sf-label {
  font-family: var(--sans);
  font-size: 0.58rem;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: var(--ink4);
  font-weight: 600;
}

.sf-val {
  font-family: var(--serif);
  font-size: 1.05rem;
  color: var(--ink);
  font-weight: 500;
}

.search-btn {
  font-family: var(--sans);
  font-size: 0.65rem;
  letter-spacing: 0.22em;
  text-transform: uppercase;
  font-weight: 600;
  padding: 0 2.5rem;
  background: var(--gold);
  color: var(--ink);
  border: none;
  cursor: pointer;
  transition: background 0.2s;
  white-space: nowrap;
}

.search-btn:hover {
  background: var(--gold2);
}

@media (max-width: 700px) {
  .search-bar {
    margin: 0 1.5rem;
    flex-direction: column;
  }

  .search-field {
    border-right: none;
    border-bottom: 1px solid var(--cream3);
  }

  .search-btn {
    padding: 1rem;
  }
}
</style>
