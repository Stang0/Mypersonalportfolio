<script setup>
import AwardsSection from './components/AwardsSection.vue'
import EducationPath from './components/EducationPath.vue'
import FAQSection from './components/FAQSection.vue'
import HeroSection from './components/HeroSection.vue'
import ProjectsSection from './components/ProjectsSection.vue'
import SiteFooter from './components/SiteFooter.vue'
import SiteHeader from './components/SiteHeader.vue'
import SkillsMarquee from './components/SkillsMarquee.vue'
</script>

<template>
  <main class="min-h-screen overflow-hidden bg-page text-text-main">
    <SiteHeader />
    <HeroSection />
    <SkillsMarquee />
    <EducationPath />
    <AwardsSection />
    <ProjectsSection />
    <FAQSection />
    <SiteFooter />
  </main>
</template>
