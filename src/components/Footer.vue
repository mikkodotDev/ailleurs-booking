<template>
  <footer>
    <div class="ft">
      <div>
        <div class="fb-name">Ailleurs</div>
        <div class="fb-tl">
          <em>Ailleurs</em> is French for "elsewhere" — the feeling of being
          exactly where you were meant to be.
        </div>
        <div class="social-row">
          <button class="sbtn">in</button>
          <button class="sbtn">ig</button>
          <button class="sbtn">𝕏</button>
          <button class="sbtn">pt</button>
        </div>
      </div>
      <div>
        <div class="fc-title">Destinations</div>
        <ul class="fl-list">
          <li><a href="#">Asia & Pacific</a></li>
          <li><a href="#">Europe</a></li>
          <li><a href="#">Africa & Middle East</a></li>
          <li><a href="#">The Americas</a></li>
          <li><a href="#">Polar expeditions</a></li>
        </ul>
      </div>
      <div>
        <div class="fc-title">Journeys</div>
        <ul class="fl-list">
          <li><a href="#">Honeymoons</a></li>
          <li><a href="#">Family adventures</a></li>
          <li><a href="#">Solo travel</a></li>
          <li><a href="#">Small group tours</a></li>
          <li><a href="#">Private charters</a></li>
        </ul>
      </div>
      <div>
        <div class="fc-title">Company</div>
        <ul class="fl-list">
          <li><a href="#">Our story</a></li>
          <li><a href="#">Travel guides</a></li>
          <li><a href="#">Responsible travel</a></li>
          <li><a href="#">Press</a></li>
          <li><a href="#">Careers</a></li>
        </ul>
      </div>
    </div>
    <div class="fb">
      <div class="fcopy">© 2026 Ailleurs Travel Ltd. All rights reserved.</div>
      <div class="fcopy">ATOL protected · ABTA member · BCorp certified</div>
    </div>
  </footer>
</template>

<script setup></script>

<style scoped>
footer {
  background: var(--ink);
  padding: 4rem 3.5rem 0;
}

.ft {
  display: grid;
  grid-template-columns: 1.8fr 1fr 1fr 1fr;
  gap: 4rem;
  padding-bottom: 3rem;
  border-bottom: 1px solid rgba(201, 185, 154, 0.1);
  margin-bottom: 0;
}

.fb-name {
  font-family: var(--serif);
  font-size: 1.8rem;
  font-weight: 300;
  letter-spacing: 0.12em;
  color: var(--gold2);
  text-transform: uppercase;
  margin-bottom: 0.8rem;
}

.fb-tl {
  font-family: var(--serif);
  font-style: italic;
  font-size: 0.9rem;
  color: var(--ink4);
  line-height: 1.6;
  margin-bottom: 1.5rem;
}

.social-row {
  display: flex;
  gap: 0.8rem;
}

.sbtn {
  width: 34px;
  height: 34px;
  border: 1px solid rgba(201, 185, 154, 0.2);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 0.75rem;
  cursor: pointer;
  color: var(--ink4);
  transition: all 0.2s;
  background: transparent;
}

.sbtn:hover {
  border-color: var(--gold);
  color: var(--gold);
}

.fc-title {
  font-family: var(--sans);
  font-size: 0.58rem;
  letter-spacing: 0.25em;
  text-transform: uppercase;
  color: var(--gold);
  margin-bottom: 1.2rem;
  font-weight: 600;
}

.fl-list {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 0.7rem;
}

.fl-list a {
  font-family: var(--sans);
  font-size: 0.78rem;
  color: var(--ink4);
  text-decoration: none;
  letter-spacing: 0.04em;
  transition: color 0.15s;
  font-weight: 300;
}

.fl-list a:hover {
  color: var(--gold2);
}

.fb {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 1rem;
  padding: 1.5rem 0;
}

.fcopy {
  font-family: var(--sans);
  font-size: 0.6rem;
  letter-spacing: 0.1em;
  color: rgba(156, 136, 120, 0.5);
}

@media (max-width: 1100px) {
  .ft {
    grid-template-columns: 1fr 1fr;
    gap: 2rem;
  }
}

@media (max-width: 700px) {
  footer {
    padding: 3rem 1.5rem 0;
  }

  .ft {
    grid-template-columns: 1fr;
  }
}
</style>
