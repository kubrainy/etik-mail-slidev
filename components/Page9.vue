<template>
  <v-click>
    <div class="hero-number">30 <span class="hero-sub">unseen samples</span></div>
  </v-click>

  <v-click>
    <div class="cat-row">
      <div class="cat-box">
        <div class="cat-name">Sert ama profesyonel</div>
        <div class="cat-count">10</div>
      </div>
      <div class="cat-box">
        <div class="cat-name">Pasif-agresif / İğneleyici</div>
        <div class="cat-count">10</div>
      </div>
      <div class="cat-box">
        <div class="cat-name">Nötr günlük iş mesajı</div>
        <div class="cat-count">10</div>
      </div>
    </div>
  </v-click>

  <v-click>
    <div class="score-row">
      <div class="score-frac">27 / 30 doğru</div>
      <div class="score-pct">%90</div>
    </div>
  </v-click>

  <v-click>
    <div class="pasif-badge">Pasif-agresif: 10/10 ✓</div>
  </v-click>

  <v-click>
    <div class="limitation">
      Sert ama profesyonel iletişim ile etik dışı iletişim arasındaki
      sınırda, model zaman zaman <span class="highlight-warn">aşırı hassas</span>
      davranabiliyor.
    </div>
  </v-click>
</template>

<style scoped>
.hero-number {
  text-align: center;
  font-size: 4rem;
  font-weight: 800;
  color: #7c3aed;
  line-height: 1;
  margin-top: 1rem;
}

.hero-sub {
  font-size: 1.2rem;
  font-weight: 500;
  opacity: 0.6;
  font-style: italic;
  display: block;
  margin-top: 0.3rem;
}

.cat-row {
  display: flex;
  justify-content: center;
  gap: 1rem;
  margin-top: 1.2rem;
  flex-wrap: wrap;
}

.cat-box {
  padding: 0.8rem 1.2rem;
  border-radius: 12px;
  background: rgba(124, 58, 237, 0.06);
  border: 1px solid rgba(124, 58, 237, 0.2);
  text-align: center;
  min-width: 170px;
}

.cat-name {
  font-size: 0.9rem;
  font-weight: 600;
  opacity: 0.8;
  margin-bottom: 0.3rem;
}

.cat-count {
  font-size: 1.4rem;
  font-weight: 800;
  color: #7c3aed;
}

.score-row {
  display: flex;
  align-items: baseline;
  justify-content: center;
  gap: 1rem;
  margin-top: 1.2rem;
}

.score-frac {
  font-size: 1.2rem;
  font-weight: 700;
  opacity: 0.8;
}

.score-pct {
  font-size: 2.2rem;
  font-weight: 800;
  color: #059669;
}

.pasif-badge {
  display: inline-block;
  margin: 0.8rem auto 0;
  padding: 0.5rem 1.4rem;
  border-radius: 999px;
  background: rgba(5, 150, 105, 0.1);
  border: 1px solid rgba(5, 150, 105, 0.35);
  color: #059669;
  font-weight: 700;
  font-size: 1rem;
}

.limitation {
  max-width: 700px;
  margin: 1.1rem auto 0;
  padding: 1rem 1.6rem;
  border-radius: 12px;
  background: rgba(220, 38, 38, 0.06);
  border: 1px solid rgba(220, 38, 38, 0.25);
  font-size: 1.05rem;
  line-height: 1.5;
  text-align: center;
}

.highlight-warn {
  color: #dc2626;
  font-weight: 700;
}
</style>