<script setup>
import NavBar from './components/NavBar.vue'
import HeroSection from './components/HeroSection.vue'
import EcosystemSection from './components/EcosystemSection.vue'
import BuildsSection from './components/BuildsSection.vue'
import ExperienceSection from './components/ExperienceSection.vue'
import ContactSection from './components/ContactSection.vue'
import FooterSection from './components/FooterSection.vue'
</script>

<template>
  <div class="min-h-screen bg-background text-on-background font-body">
    <NavBar />
    <main>
      <HeroSection />
      <EcosystemSection />
      <BuildsSection />
      <ExperienceSection />
      <ContactSection />
    </main>
    <FooterSection />
  </div>
</template>
