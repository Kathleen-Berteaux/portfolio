<template>
  <footer class="footer">
    <div class="container footer-inner">
      <div class="footer-brand">
        <span class="footer-logo">KB</span>
        <span class="footer-name">Kathleen Berteaux</span>
        <span class="footer-title">Assistante de Gestion</span>
      </div>
      <p class="footer-copy">© 2025 Kathleen Berteaux · Tous droits réservés</p>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  background: var(--primary-dark);
  color: rgba(255,255,255,0.7);
  padding: 2rem 0;
}

.footer-inner {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 1rem;
}

.footer-brand {
  display: flex;
  align-items: center;
  gap: 0.75rem;
}

.footer-logo {
  font-family: 'Playfair Display', serif;
  font-size: 1.25rem;
  font-weight: 700;
  color: var(--accent);
  background: rgba(255,255,255,0.1);
  width: 38px;
  height: 38px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  letter-spacing: 1px;
}

.footer-name {
  font-weight: 600;
  color: #fff;
  font-size: 0.95rem;
}

.footer-title {
  font-size: 0.8rem;
  color: rgba(255,255,255,0.5);
}

.footer-copy {
  font-size: 0.8rem;
}

@media (max-width: 600px) {
  .footer-inner { flex-direction: column; text-align: center; }
  .footer-brand { flex-direction: column; }
}
</style>
