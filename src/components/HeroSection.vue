<script setup>
const scrollTo = (id) => document.getElementById(id)?.scrollIntoView({ behavior: 'smooth' })
const downloadCV = () => window.print()
</script>

<template>
  <section id="accueil" class="hero">
    <div class="container hero-inner">
      <div class="hero-text">
        <p class="hero-subtitle">Assistante de Gestion</p>
        <h1 class="hero-name">Kathleen<br>Berteaux</h1>
        <p class="hero-desc">
          Assistante de direction expérimentée, spécialisée en coordination administrative
          et suivi de projets, avec une expérience significative dans les secteurs public et privé.
          Reconnue pour l'optimisation des processus et la gestion simultanée de dossiers complexes.
        </p>
        <div class="hero-actions">
          <button class="btn-primary" @click="scrollTo('experiences')">Voir mon parcours</button>
          <button class="btn-outline" @click="scrollTo('contact')">Me contacter</button>
          <button class="btn-outline" @click="downloadCV">Télécharger mon CV (PDF)</button>
        </div>
        <div class="hero-badges">
          <span class="badge">📍 Schiltigheim, France</span>
          <span class="badge">✉️ berteaux.kathleen@gmail.com</span>
          <span class="badge">📞 06.65.94.56.02</span>
        </div>
      </div>
      <div class="hero-image-wrap">
        <div class="hero-image-ring">
          <div class="hero-avatar">
            <span>KB</span>
          </div>
        </div>
        <div class="hero-deco deco-1"></div>
        <div class="hero-deco deco-2"></div>
      </div>
    </div>
    <div class="hero-scroll" @click="scrollTo('competences')">
      <span>↓</span>
    </div>
  </section>
</template>

<style scoped>
.hero {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 6rem 0 3rem;
  background: linear-gradient(135deg, #FDFAF6 60%, #F0E6D6 100%);
  position: relative;
}

.hero-inner {
  display: flex;
  align-items: center;
  gap: 4rem;
}

.hero-text {
  flex: 1;
}

.hero-subtitle {
  font-size: 1rem;
  font-weight: 600;
  color: var(--primary-light);
  letter-spacing: 3px;
  text-transform: uppercase;
  margin-bottom: 1rem;
}

.hero-name {
  font-family: 'Playfair Display', serif;
  font-size: clamp(2.5rem, 5vw, 4rem);
  font-weight: 700;
  color: var(--primary-dark);
  line-height: 1.15;
  margin-bottom: 1.5rem;
}

.hero-desc {
  font-size: 1.05rem;
  color: var(--text-light);
  line-height: 1.8;
  max-width: 520px;
  margin-bottom: 2rem;
}

.hero-actions {
  display: flex;
  gap: 1rem;
  margin-bottom: 2rem;
  flex-wrap: wrap;
}

.btn-primary {
  padding: 0.85rem 2rem;
  background: var(--primary);
  color: #fff;
  border: none;
  border-radius: 50px;
  font-family: 'Inter', sans-serif;
  font-weight: 600;
  font-size: 0.95rem;
  cursor: pointer;
  transition: background 0.2s, transform 0.2s;
}

.btn-primary:hover {
  background: var(--primary-dark);
  transform: translateY(-2px);
}

.btn-outline {
  padding: 0.85rem 2rem;
  background: transparent;
  color: var(--primary);
  border: 2px solid var(--primary-light);
  border-radius: 50px;
  font-family: 'Inter', sans-serif;
  font-weight: 600;
  font-size: 0.95rem;
  cursor: pointer;
  transition: all 0.2s;
}

.btn-outline:hover {
  background: var(--primary);
  color: #fff;
  border-color: var(--primary);
  transform: translateY(-2px);
}

.hero-badges {
  display: flex;
  flex-wrap: wrap;
  gap: 0.75rem;
}

.badge {
  display: inline-flex;
  align-items: center;
  gap: 0.4rem;
  font-size: 0.82rem;
  color: var(--text-light);
  background: rgba(196, 168, 130, 0.15);
  padding: 0.4rem 0.9rem;
  border-radius: 50px;
  border: 1px solid var(--border);
}

.hero-image-wrap {
  position: relative;
  flex-shrink: 0;
}

.hero-image-ring {
  width: 280px;
  height: 280px;
  border-radius: 50%;
  background: linear-gradient(135deg, var(--primary-light), var(--accent));
  padding: 6px;
  position: relative;
  z-index: 1;
}

.hero-avatar {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  background: linear-gradient(135deg, #E8D5BE, #C9A87A);
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: 'Playfair Display', serif;
  font-size: 4rem;
  font-weight: 700;
  color: var(--primary-dark);
}

.hero-deco {
  position: absolute;
  border-radius: 50%;
  opacity: 0.25;
}

.deco-1 {
  width: 120px;
  height: 120px;
  background: var(--primary-light);
  top: -20px;
  right: -20px;
  z-index: 0;
}

.deco-2 {
  width: 70px;
  height: 70px;
  background: var(--accent);
  bottom: -10px;
  left: -10px;
  z-index: 0;
}

.hero-scroll {
  position: absolute;
  bottom: 2rem;
  left: 50%;
  transform: translateX(-50%);
  width: 40px;
  height: 40px;
  border: 2px solid var(--primary-light);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  animation: bounce 2s infinite;
  color: var(--primary);
  font-size: 1rem;
}

@keyframes bounce {
  0%, 100% { transform: translateX(-50%) translateY(0); }
  50% { transform: translateX(-50%) translateY(-8px); }
}

@media (max-width: 768px) {
  .hero-inner {
    flex-direction: column-reverse;
    text-align: center;
    gap: 2rem;
  }
  .hero-desc { max-width: 100%; }
  .hero-actions { justify-content: center; }
  .hero-badges { justify-content: center; }
  .hero-image-ring { width: 200px; height: 200px; }
  .hero-avatar { font-size: 2.8rem; }
}
</style>
