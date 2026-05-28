<script setup>
const experiences = [
  {
    title: 'Assistante de gestion',
    company: 'Appligos-Opendev',
    period: 'Déc. 2025 – Aujourd\'hui',
    location: 'Strasbourg, France',
    current: true,
    tasks: [
      'Gestion administrative des projets : réponse aux appels d\'offres publics, rédaction et suivi des contrats de maintenance',
      'Suivi des commandes et facturation (création de bons de commande, contrôle et émission des factures)',
      'Interface avec les clients : gestion des échanges téléphoniques et e-mails',
      'Suivi rigoureux des dossiers administratifs et mise à jour des documents',
    ],
    highlight: null,
  },
  {
    title: 'Assistante du Directeur de projets',
    company: 'Bruneau Electrique',
    period: 'Oct. 2023 – Juil. 2025',
    location: 'Montréal, Canada',
    current: false,
    tasks: [
      'Suivi administratif et opérationnel de 4 projets de rénovation électrique',
      'Gestion des approvisionnements : commandes, réception et validation des matériaux',
      'Suivi des heures des équipes et mise à jour des données de chantier',
      'Gestion documentaire : mise en ligne et archivage des plans et documents techniques',
      'Gestion de la facturation : réception des quittances et émission des factures',
    ],
    highlight: 'Optimisation du suivi des projets via les logiciels Horizon et Caméléon, contribuant à un gain de temps et une meilleure maîtrise des coûts',
  },
  {
    title: 'Assistante de Direction',
    company: 'Hôtel de Ville de Chelles',
    period: 'Avr. 2017 – Juil. 2023',
    location: 'Chelles, France',
    current: false,
    badge: '6 ans d\'expérience',
    tasks: [
      'Gestion des agendas des élus locaux et du Directeur de Cabinet',
      'Organisation de réunions (logistique, supports, comptes rendus)',
      'Suivi des demandes administrés et gestion des priorités',
      'Rédaction de documents officiels à destination du Maire et des élus',
      'Interface avec les interlocuteurs internes et externes',
      'Gestion des fournitures administratives',
    ],
    highlight: null,
    achievements: [
      'Formation de 3 assistantes, contribuant à la montée en compétence du service',
      'Mise en place de courriers types → gain de temps significatif',
      'Organisation de dispositifs terrain ("tours de ville") → amélioration de la qualité de service',
    ],
  },
]

const extras = [
  { title: 'Assistante médicale', period: '2017' },
  { title: 'Conseillère de vente', period: '2014 – 2017' },
  { title: 'Adjointe du Chef de rayon (alternance)', period: '2012 – 2014' },
]
</script>

<template>
  <section id="experiences">
    <div class="container">
      <h2 class="section-title">Expériences Professionnelles</h2>

      <div class="timeline">
        <div
          v-for="(exp, i) in experiences"
          :key="i"
          class="timeline-item"
          :class="{ current: exp.current }"
        >
          <div class="timeline-dot"></div>
          <div class="timeline-card">
            <div class="card-header">
              <div class="card-header-left">
                <span v-if="exp.current" class="current-badge">En poste</span>
                <span v-if="exp.badge" class="years-badge">{{ exp.badge }}</span>
                <h3 class="card-title">{{ exp.title }}</h3>
                <p class="card-company">{{ exp.company }}</p>
              </div>
              <div class="card-header-right">
                <span class="card-period">{{ exp.period }}</span>
                <span class="card-location">📍 {{ exp.location }}</span>
              </div>
            </div>

            <ul class="task-list">
              <li v-for="task in exp.tasks" :key="task">{{ task }}</li>
            </ul>

            <div v-if="exp.highlight" class="highlight-box">
              <span class="highlight-icon">✨</span>
              <em>{{ exp.highlight }}</em>
            </div>

            <div v-if="exp.achievements" class="achievements">
              <p class="achievements-title">Réalisations clés :</p>
              <ul>
                <li v-for="a in exp.achievements" :key="a">{{ a }}</li>
              </ul>
            </div>
          </div>
        </div>
      </div>

      <div class="extras-block">
        <h3 class="extras-title">Expériences complémentaires</h3>
        <div class="extras-list">
          <div v-for="e in extras" :key="e.title" class="extra-item">
            <span class="extra-title">{{ e.title }}</span>
            <span class="extra-period">{{ e.period }}</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.timeline {
  position: relative;
  padding-left: 2rem;
  margin-bottom: 3rem;
}

.timeline::before {
  content: '';
  position: absolute;
  left: 8px;
  top: 0;
  bottom: 0;
  width: 2px;
  background: linear-gradient(to bottom, var(--primary-light), var(--border));
}

.timeline-item {
  position: relative;
  margin-bottom: 2.5rem;
}

.timeline-dot {
  position: absolute;
  left: -2rem;
  top: 1.5rem;
  width: 18px;
  height: 18px;
  border-radius: 50%;
  background: var(--border);
  border: 3px solid var(--bg);
  box-shadow: 0 0 0 2px var(--primary-light);
}

.timeline-item.current .timeline-dot {
  background: var(--primary);
  box-shadow: 0 0 0 3px var(--primary-light), 0 0 0 5px rgba(139,115,85,0.15);
}

.timeline-card {
  background: var(--bg-card);
  border-radius: var(--radius-lg);
  padding: 1.75rem 2rem;
  border: 1px solid var(--border);
  box-shadow: var(--shadow);
  transition: box-shadow 0.2s;
}

.timeline-card:hover {
  box-shadow: var(--shadow-hover);
}

.card-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  gap: 1rem;
  margin-bottom: 1.25rem;
  flex-wrap: wrap;
}

.current-badge {
  display: inline-block;
  background: var(--primary);
  color: #fff;
  font-size: 0.72rem;
  font-weight: 600;
  padding: 0.2rem 0.7rem;
  border-radius: 50px;
  letter-spacing: 1px;
  text-transform: uppercase;
  margin-bottom: 0.5rem;
}

.years-badge {
  display: inline-block;
  background: var(--bg-section);
  color: var(--primary);
  font-size: 0.75rem;
  font-weight: 600;
  padding: 0.2rem 0.7rem;
  border-radius: 50px;
  border: 1px solid var(--border);
  margin-bottom: 0.5rem;
}

.card-title {
  font-family: 'Playfair Display', serif;
  font-size: 1.2rem;
  font-weight: 700;
  color: var(--primary-dark);
  margin-bottom: 0.25rem;
}

.card-company {
  font-size: 0.92rem;
  font-weight: 600;
  color: var(--primary);
}

.card-header-right {
  text-align: right;
  display: flex;
  flex-direction: column;
  gap: 0.3rem;
  flex-shrink: 0;
}

.card-period {
  font-size: 0.85rem;
  font-weight: 600;
  color: var(--text-light);
}

.card-location {
  font-size: 0.8rem;
  color: var(--text-muted);
}

.task-list {
  list-style: none;
  padding: 0;
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  margin-bottom: 1rem;
}

.task-list li {
  font-size: 0.9rem;
  color: var(--text-light);
  padding-left: 1.2rem;
  position: relative;
}

.task-list li::before {
  content: '›';
  position: absolute;
  left: 0;
  color: var(--primary-light);
  font-weight: 700;
}

.highlight-box {
  display: flex;
  gap: 0.75rem;
  align-items: flex-start;
  background: linear-gradient(135deg, #FFF8F0, #F5EFE6);
  border-left: 3px solid var(--primary-light);
  padding: 0.9rem 1.1rem;
  border-radius: 0 var(--radius) var(--radius) 0;
  margin-bottom: 1rem;
  font-size: 0.88rem;
  color: var(--text-light);
  font-style: italic;
}

.highlight-icon { font-style: normal; flex-shrink: 0; }

.achievements {
  margin-top: 0.75rem;
}

.achievements-title {
  font-size: 0.82rem;
  font-weight: 600;
  color: var(--primary);
  margin-bottom: 0.5rem;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.achievements ul {
  list-style: none;
  padding: 0;
  display: flex;
  flex-direction: column;
  gap: 0.4rem;
}

.achievements li {
  font-size: 0.85rem;
  color: var(--text-light);
  padding-left: 1.2rem;
  position: relative;
  font-style: italic;
}

.achievements li::before {
  content: '—';
  position: absolute;
  left: 0;
  color: var(--primary-light);
}

.extras-block {
  background: var(--bg-card);
  border-radius: var(--radius-lg);
  padding: 1.75rem 2rem;
  border: 1px solid var(--border);
}

.extras-title {
  font-family: 'Inter', sans-serif;
  font-size: 1rem;
  font-weight: 600;
  color: var(--primary-dark);
  margin-bottom: 1.25rem;
}

.extras-list {
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}

.extra-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0.6rem 0;
  border-bottom: 1px dashed var(--border);
  font-size: 0.9rem;
}

.extra-item:last-child { border-bottom: none; }

.extra-title { color: var(--text-light); font-weight: 500; }
.extra-period { color: var(--text-muted); font-size: 0.82rem; }

@media (max-width: 768px) {
  .card-header { flex-direction: column; }
  .card-header-right { text-align: left; }
  .timeline { padding-left: 1.5rem; }
}
</style>
