<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import NavBar from './components/NavBar.vue'
import HeroSection from './components/HeroSection.vue'
import SkillsSection from './components/SkillsSection.vue'
import ExperienceSection from './components/ExperienceSection.vue'
import EducationSection from './components/EducationSection.vue'
import ContactSection from './components/ContactSection.vue'
import FooterSection from './components/FooterSection.vue'

const activeSection = ref('accueil')

const sections = ['accueil', 'competences', 'experiences', 'formation', 'contact']

const handleScroll = () => {
  const scrollY = window.scrollY + 100
  for (const id of sections) {
    const el = document.getElementById(id)
    if (el && scrollY >= el.offsetTop) {
      activeSection.value = id
    }
  }
}

onMounted(() => window.addEventListener('scroll', handleScroll))
onUnmounted(() => window.removeEventListener('scroll', handleScroll))
</script>

<template>
  <NavBar :active="activeSection" />
  <main>
    <HeroSection />
    <SkillsSection />
    <ExperienceSection />
    <EducationSection />
    <ContactSection />
  </main>
  <FooterSection />
</template>
