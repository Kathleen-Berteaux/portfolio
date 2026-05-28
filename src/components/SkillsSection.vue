<script setup>
const skills = [
  { icon: '📋', title: 'Coordination administrative', desc: 'Gestion d\'agendas complexes, organisation de réunions, suivi des dossiers administratifs.' },
  { icon: '📁', title: 'Suivi de projets', desc: 'Gestion multi-dossiers, suivi opérationnel de projets, mise à jour des données de chantier.' },
  { icon: '📝', title: 'Gestion documentaire', desc: 'Rédaction professionnelle, archivage, mise en ligne de documents techniques et officiels.' },
  { icon: '🤝', title: 'Relation clients / usagers', desc: 'Interface téléphonique et e-mail, gestion des priorités, accueil et traitement des demandes.' },
  { icon: '💰', title: 'Facturation & suivi financier', desc: 'Création de bons de commande, contrôle et émission de factures, suivi des commandes.' },
  { icon: '⚙️', title: 'Optimisation des processus', desc: 'Amélioration organisationnelle, mise en place de courriers types, formation d\'assistantes.' },
]

const tools = [
  { name: 'Pack Office', level: 95 },
  { name: 'Outlook', level: 95 },
  { name: 'Dolibarr', level: 85 },
  { name: 'Horizon', level: 80 },
  { name: 'Caméléon', level: 80 },
  { name: 'Elise', level: 75 },
  { name: '4D', level: 75 },
  { name: 'Virtuose / E-atal', level: 70 },
]

const qualities = [
  { icon: '😊', label: 'Sociable' },
  { icon: '🎯', label: 'Rigoureuse' },
  { icon: '🗂️', label: 'Organisée' },
  { icon: '💬', label: 'Sens des relations' },
  { icon: '🔄', label: 'Capacité d\'adaptation' },
  { icon: '☎️', label: 'Gestion des appels' },
]
</script>

<template>
  <section id="competences" class="skills-section">
    <div class="container">
      <h2 class="section-title">Compétences</h2>

      <div class="skills-grid">
        <div v-for="skill in skills" :key="skill.title" class="skill-card">
          <div class="skill-icon">{{ skill.icon }}</div>
          <h3>{{ skill.title }}</h3>
          <p>{{ skill.desc }}</p>
        </div>
      </div>

      <div class="tools-block">
        <h3 class="sub-title">Logiciels & Outils</h3>
        <div class="tools-list">
          <div v-for="tool in tools" :key="tool.name" class="tool-item">
            <div class="tool-header">
              <span class="tool-name">{{ tool.name }}</span>
              <span class="tool-pct">{{ tool.level }}%</span>
            </div>
            <div class="tool-bar">
              <div class="tool-fill" :style="{ width: tool.level + '%' }"></div>
            </div>
          </div>
        </div>
      </div>

      <div class="qualities-block">
        <h3 class="sub-title">Qualités personnelles</h3>
        <div class="qualities-list">
          <span v-for="q in qualities" :key="q.label" class="quality-tag">
            <span>{{ q.icon }}</span> {{ q.label }}
          </span>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.skills-section {
  background: var(--bg-section);
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 1.5rem;
  margin-bottom: 3.5rem;
}

.skill-card {
  background: var(--bg-card);
  border-radius: var(--radius);
  padding: 1.75rem;
  border: 1px solid var(--border);
  box-shadow: var(--shadow);
  transition: transform 0.2s, box-shadow 0.2s;
}

.skill-card:hover {
  transform: translateY(-4px);
  box-shadow: var(--shadow-hover);
}

.skill-icon {
  font-size: 2rem;
  margin-bottom: 0.75rem;
}

.skill-card h3 {
  font-family: 'Inter', sans-serif;
  font-size: 1rem;
  font-weight: 600;
  color: var(--primary-dark);
  margin-bottom: 0.5rem;
}

.skill-card p {
  font-size: 0.88rem;
  color: var(--text-muted);
  line-height: 1.6;
}

.tools-block,
.qualities-block {
  background: var(--bg-card);
  border-radius: var(--radius-lg);
  padding: 2rem 2.5rem;
  border: 1px solid var(--border);
  margin-bottom: 2rem;
}

.sub-title {
  font-family: 'Inter', sans-serif;
  font-size: 1.1rem;
  font-weight: 600;
  color: var(--primary-dark);
  margin-bottom: 1.5rem;
  padding-bottom: 0.5rem;
  border-bottom: 2px solid var(--border);
}

.tools-list {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 1rem 2rem;
}

.tool-header {
  display: flex;
  justify-content: space-between;
  margin-bottom: 0.4rem;
}

.tool-name {
  font-size: 0.88rem;
  font-weight: 500;
  color: var(--text);
}

.tool-pct {
  font-size: 0.8rem;
  color: var(--text-muted);
}

.tool-bar {
  height: 6px;
  background: var(--border);
  border-radius: 3px;
  overflow: hidden;
}

.tool-fill {
  height: 100%;
  background: linear-gradient(90deg, var(--primary-light), var(--primary));
  border-radius: 3px;
  transition: width 1s ease;
}

.qualities-list {
  display: flex;
  flex-wrap: wrap;
  gap: 0.75rem;
}

.quality-tag {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.5rem 1.1rem;
  background: var(--bg-section);
  border: 1px solid var(--border);
  border-radius: 50px;
  font-size: 0.88rem;
  font-weight: 500;
  color: var(--text-light);
}
</style>
