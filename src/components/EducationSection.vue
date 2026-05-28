<script setup>
const diplomas = [
  {
    icon: '🎓',
    degree: 'BTS Management des Unités Commerciales',
    detail: 'Alternance',
    school: 'CFA Codis',
    location: 'Paris, France',
    year: '2012 – 2014',
  },
  {
    icon: '📚',
    degree: 'Baccalauréat Économique et Social',
    detail: 'Spécialité Mathématiques',
    school: 'Lycée Gaston Bachelard',
    location: 'Chelles, France',
    year: '2009 – 2010',
  },
]
</script>

<template>
  <section id="formation" class="education-section">
    <div class="container">
      <h2 class="section-title">Formation</h2>

      <div class="education-grid">
        <div v-for="d in diplomas" :key="d.degree" class="edu-card">
          <div class="edu-icon">{{ d.icon }}</div>
          <div class="edu-body">
            <span class="edu-year">{{ d.year }}</span>
            <h3 class="edu-degree">{{ d.degree }}</h3>
            <p class="edu-detail">{{ d.detail }}</p>
            <div class="edu-school">
              <span class="school-name">{{ d.school }}</span>
              <span class="school-loc">📍 {{ d.location }}</span>
            </div>
          </div>
        </div>
      </div>

      <div class="learning-block">
        <div class="learning-icon">💡</div>
        <div>
          <h3>Formation continue</h3>
          <p>
            Mise à jour régulière des compétences logicielles (Dolibarr, Horizon, Caméléon)
            et adaptation continue aux outils métiers dans les secteurs public et privé.
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.education-section {
  background: var(--bg-section);
}

.education-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 1.5rem;
  margin-bottom: 2rem;
}

.edu-card {
  background: var(--bg-card);
  border-radius: var(--radius-lg);
  padding: 2rem;
  border: 1px solid var(--border);
  box-shadow: var(--shadow);
  display: flex;
  gap: 1.25rem;
  align-items: flex-start;
  transition: transform 0.2s, box-shadow 0.2s;
}

.edu-card:hover {
  transform: translateY(-4px);
  box-shadow: var(--shadow-hover);
}

.edu-icon {
  font-size: 2.5rem;
  flex-shrink: 0;
  width: 56px;
  height: 56px;
  background: var(--bg-section);
  border-radius: var(--radius);
  display: flex;
  align-items: center;
  justify-content: center;
}

.edu-year {
  display: inline-block;
  font-size: 0.75rem;
  font-weight: 600;
  color: var(--primary);
  background: rgba(196,168,130,0.18);
  padding: 0.2rem 0.7rem;
  border-radius: 50px;
  margin-bottom: 0.6rem;
}

.edu-degree {
  font-family: 'Playfair Display', serif;
  font-size: 1.1rem;
  font-weight: 700;
  color: var(--primary-dark);
  margin-bottom: 0.25rem;
}

.edu-detail {
  font-size: 0.85rem;
  color: var(--primary);
  font-style: italic;
  margin-bottom: 0.75rem;
}

.edu-school {
  display: flex;
  flex-direction: column;
  gap: 0.2rem;
}

.school-name {
  font-size: 0.88rem;
  font-weight: 600;
  color: var(--text-light);
}

.school-loc {
  font-size: 0.8rem;
  color: var(--text-muted);
}

.learning-block {
  background: var(--bg-card);
  border-radius: var(--radius-lg);
  padding: 1.75rem 2rem;
  border: 1px solid var(--border);
  display: flex;
  gap: 1.25rem;
  align-items: flex-start;
}

.learning-icon {
  font-size: 2rem;
  flex-shrink: 0;
}

.learning-block h3 {
  font-family: 'Inter', sans-serif;
  font-size: 1rem;
  font-weight: 600;
  color: var(--primary-dark);
  margin-bottom: 0.4rem;
}

.learning-block p {
  font-size: 0.9rem;
  color: var(--text-muted);
  line-height: 1.6;
}
</style>
