<script setup>
  import Bottomcta from './components/Bottomcta.vue';
  import Header from './components/Header.vue';
  import Hero from './components/Hero.vue';
  import PageFooter from './components/PageFooter.vue';
  import Metrics from './components/Metrics.vue';
  import Features from './components/Features.vue';
import Testimonials from './components/Testimonials.vue';
import Usedby from './components/Usedby.vue';
</script>

<template>
  <Header></Header>
  <main>
    <Hero />
    <Features />
    <Testimonials />
    <Metrics />
    <Usedby />
    <Bottomcta />
  </main>
  <PageFooter />
</template>

<style scoped>

</style>