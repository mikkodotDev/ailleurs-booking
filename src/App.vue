<template>
  <div id="app">
    <Navigation />
    <Hero />
    <SearchBar />
    <StatsStrip />
    <DestinationCards />
    <FeaturedJourney />
    <Experiences />
    <Testimonial />
    <WhyUs />
    <BookingCTA />
    <Footer />
  </div>
</template>

<script setup>
import Navigation from "./components/Navigation.vue";
import Hero from "./components/Hero.vue";
import SearchBar from "./components/SearchBar.vue";
import StatsStrip from "./components/StatsStrip.vue";
import DestinationCards from "./components/DestinationCards.vue";
import FeaturedJourney from "./components/FeaturedJourney.vue";
import Experiences from "./components/Experiences.vue";
import Testimonial from "./components/Testimonial.vue";
import WhyUs from "./components/WhyUs.vue";
import BookingCTA from "./components/BookingCTA.vue";
import Footer from "./components/Footer.vue";
</script>

<style scoped>
#app {
  width: 100%;
  overflow-x: hidden;
}
</style>
