<script setup>
const contacts = [
  { icon: '📞', label: 'Téléphone', value: '06.65.94.56.02', href: 'tel:0665945602' },
  { icon: '✉️', label: 'Email', value: 'berteaux.kathleen@gmail.com', href: 'mailto:berteaux.kathleen@gmail.com' },
  ]
</script>

<template>
  <section id="contact">
    <div class="container">
      <h2 class="section-title">Contact</h2>

      <div class="contact-layout">
        <div class="contact-intro">
          <h3>Travaillons ensemble</h3>
          <p>N'hésitez pas à me contacter afin que nous puissions faire un point sur les problématiques 
          que vous rencontrez et les besoins en terme administratifs que vous avez. 
          Je saurai trouver les actions à mettre en place afin de travailler de manière efficiente à votre réussite.
          </p>
          <div class="availability">
            <span class="dot"></span>
            <span>Disponible sur toute la France et la Suisse</span>
          </div>
        </div>

        <div class="contact-cards">
          <a
            v-for="c in contacts"
            :key="c.label"
            :href="c.href || undefined"
            class="contact-card"
            :class="{ clickable: !!c.href }"
          >
            <div class="contact-icon">{{ c.icon }}</div>
            <div>
              <p class="contact-label">{{ c.label }}</p>
              <p class="contact-value" style="white-space: pre-line">{{ c.value }}</p>
            </div>
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.contact-layout {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 3rem;
  align-items: center;
}

.contact-intro h3 {
  font-family: 'Playfair Display', serif;
  font-size: 1.6rem;
  font-weight: 700;
  color: var(--primary-dark);
  margin-bottom: 1rem;
}

.contact-intro p {
  font-size: 1rem;
  color: var(--text-light);
  line-height: 1.8;
  margin-bottom: 1.5rem;
}

.availability {
  display: inline-flex;
  align-items: center;
  gap: 0.6rem;
  font-size: 0.88rem;
  font-weight: 500;
  color: #4A8C5C;
  background: rgba(74,140,92,0.1);
  padding: 0.4rem 1rem;
  border-radius: 50px;
  border: 1px solid rgba(74,140,92,0.25);
}

.dot {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background: #4A8C5C;
  animation: pulse 2s infinite;
}

@keyframes pulse {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.4; }
}

.contact-cards {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.contact-card {
  display: flex;
  align-items: center;
  gap: 1.25rem;
  background: var(--bg-card);
  border: 1px solid var(--border);
  border-radius: var(--radius);
  padding: 1.25rem 1.5rem;
  box-shadow: var(--shadow);
  transition: transform 0.2s, box-shadow 0.2s;
  text-decoration: none;
}

.contact-card.clickable:hover {
  transform: translateX(6px);
  box-shadow: var(--shadow-hover);
}

.contact-icon {
  font-size: 1.5rem;
  width: 44px;
  height: 44px;
  background: var(--bg-section);
  border-radius: var(--radius);
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
}

.contact-label {
  font-size: 0.75rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 1px;
  color: var(--text-muted);
  margin-bottom: 0.2rem;
}

.contact-value {
  font-size: 0.95rem;
  font-weight: 500;
  color: var(--text);
}

@media (max-width: 768px) {
  .contact-layout {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
}
</style>
