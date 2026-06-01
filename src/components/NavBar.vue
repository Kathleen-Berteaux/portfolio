<script setup>
import { ref } from 'vue'

defineProps({ active: String })

const menuOpen = ref(false)

const links = [
  { id: 'accueil', label: 'Accueil' },
  { id: 'competences', label: 'Compétences' },
  { id: 'experiences', label: 'Expériences' },
  { id: 'formations', label: 'Formations' },
  { id: 'contact', label: 'Contact' },
]

const scrollTo = (id) => {
  menuOpen.value = false
  document.getElementById(id)?.scrollIntoView({ behavior: 'smooth' })
}
</script>

<template>
  <nav class="navbar">
    <div class="nav-inner container">
      <span class="nav-logo" @click="scrollTo('accueil')">KB</span>
      <button class="burger" @click="menuOpen = !menuOpen" :class="{ open: menuOpen }">
        <span></span><span></span><span></span>
      </button>
      <ul class="nav-links" :class="{ open: menuOpen }">
        <li v-for="link in links" :key="link.id">
          <a
            :class="{ active: active === link.id }"
            @click.prevent="scrollTo(link.id)"
            href="#"
          >{{ link.label }}</a>
        </li>
      </ul>
    </div>
  </nav>
</template>

<style scoped>
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 100;
  background: rgba(253, 250, 246, 0.95);
  backdrop-filter: blur(10px);
  border-bottom: 1px solid var(--border);
  height: 64px;
}

.nav-inner {
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 64px;
}

.nav-logo {
  font-family: 'Playfair Display', serif;
  font-size: 1.5rem;
  font-weight: 700;
  color: var(--primary);
  cursor: pointer;
  letter-spacing: 2px;
}

.nav-links {
  list-style: none;
  display: flex;
  gap: 2rem;
}

.nav-links a {
  font-size: 0.9rem;
  font-weight: 500;
  color: var(--text-light);
  padding-bottom: 4px;
  border-bottom: 2px solid transparent;
  transition: color 0.2s, border-color 0.2s;
  cursor: pointer;
}

.nav-links a:hover,
.nav-links a.active {
  color: var(--primary);
  border-bottom-color: var(--primary-light);
}

.burger {
  display: none;
  flex-direction: column;
  gap: 5px;
  background: none;
  border: none;
  cursor: pointer;
  padding: 4px;
}

.burger span {
  display: block;
  width: 24px;
  height: 2px;
  background: var(--primary);
  transition: all 0.3s;
}

@media (max-width: 768px) {
  .burger { display: flex; }

  .nav-links {
    display: none;
    position: absolute;
    top: 64px;
    left: 0;
    right: 0;
    background: var(--bg);
    flex-direction: column;
    gap: 0;
    border-bottom: 1px solid var(--border);
    padding: 1rem 0;
  }

  .nav-links.open { display: flex; }

  .nav-links li a {
    display: block;
    padding: 0.75rem 2rem;
    border-bottom: none;
  }
}
</style>
