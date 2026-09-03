<template>
  <div class="stage-area">
    <div class="stat-stage" v-click.hide="1">
      <div class="big-number">645</div>
      <div class="subtitle">samples</div>
      <div class="split-row">
        <span class="split split-unethical">323 etik dışı</span>
        <span class="split-sep">|</span>
        <span class="split split-ethical">322 etik</span>
      </div>
    </div>

    <div class="metrics-area" v-click="1" v-click.hide="2">
      <div class="metrics-grid">
        <div class="metric-card">
          <div class="metric-label">Doğruluk</div>
          <div class="metric-value">99.845%</div>
        </div>
        <div class="metric-card">
          <div class="metric-label">Kesinlik</div>
          <div class="metric-value">100%</div>
        </div>
        <div class="metric-card">
          <div class="metric-label">Duyarlılık</div>
          <div class="metric-value">99.690%</div>
        </div>
        <div class="metric-card">
          <div class="metric-label">F1</div>
          <div class="metric-value">99.845%</div>
        </div>
      </div>
      <div class="metrics-note">645 örnek</div>
    </div>

    <div class="matrix-area" v-click="2">
      <div class="matrix-wrap">
  <table class="matrix">
    <thead>
      <tr>
        <th class="corner"></th>
        <th class="corner"></th>
        <th colspan="2">Tahmin</th>
      </tr>
      <tr>
        <th class="corner"></th>
        <th class="corner"></th>
        <th>Etik</th>
        <th>Etik Dışı</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <th rowspan="2" class="matrix-side">Gerçek</th>
        <th>Etik</th>
        <td class="cell-ok">322</td>
        <td class="cell-zero">0</td>
      </tr>
      <tr>
        <th>Etik Dışı</th>
        <td class="cell-warn">1</td>
        <td class="cell-ok">322</td>
      </tr>
    </tbody>
  </table>
</div>

      <div class="final-line" v-click="3">
        Yalnızca <span class="highlight-warn">1 yanlış negatif</span> ·
        <span class="highlight-ok">0 yanlış pozitif</span>
      </div>
    </div>
  </div>
</template>

<style scoped>
.stage-area {
  position: relative;
  min-height: 400px;
  margin-top: 1rem;
}

.stage-area :deep(.slidev-vclick-hidden) {
  transition-duration: 0s !important;
}

.stat-stage {
  position: absolute;
  inset: 0;
  margin: auto;
  width: fit-content;
  height: fit-content;
  text-align: center;
}

.big-number {
  font-size: 5rem;
  font-weight: 800;
  color: #7c3aed;
  line-height: 1;
  letter-spacing: -0.02em;
}

.subtitle {
  font-size: 1.2rem;
  opacity: 0.6;
  margin-top: 0.2rem;
  font-style: italic;
}

.split-row {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 1rem;
  margin-top: 1.2rem;
  font-size: 1.15rem;
  font-weight: 700;
}

.split-unethical {
  color: #dc2626;
}

.split-ethical {
  color: #059669;
}

.split-sep {
  opacity: 0.3;
  font-weight: 400;
}

.metrics-area {
  position: absolute;
  inset: 0;
  margin: auto;
  width: fit-content;
  height: fit-content;
  text-align: center;
}

.metrics-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 1rem 2.5rem;
}

.metric-card {
  text-align: center;
}

.metric-label {
  font-size: 1.05rem;
  opacity: 0.6;
  font-weight: 600;
  letter-spacing: 0.05em;
}

.metric-value {
  font-size: 2.9rem;
  font-weight: 800;
  color: #7c3aed;
  line-height: 1.1;
}

.metrics-note {
  margin-top: 0.6rem;
  font-size: 1.05rem;
  opacity: 0.5;
  font-style: italic;
}

.matrix-area {
  position: absolute;
  inset: 0;
  margin: auto;
  width: fit-content;
  height: fit-content;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
}

.matrix-wrap {
  margin-top: 0;
}

.matrix {
  border-collapse: collapse;
  font-size: 1.2rem;
}

.matrix th, .matrix td {
  padding: 0.6rem 1.4rem;
}

.matrix thead th {
  font-weight: 700;
  opacity: 0.7;
  font-size: 1rem;
}

.matrix tbody th {
  font-weight: 700;
  opacity: 0.75;
  text-align: right;
  padding-right: 1.2rem;
}

.cell-ok {
  background: rgba(16, 185, 129, 0.12);
  color: #059669;
  font-weight: 700;
  border-radius: 6px;
}

.cell-zero {
  background: rgba(120, 120, 120, 0.06);
  opacity: 0.5;
}

.cell-warn {
  background: rgba(220, 38, 38, 0.12);
  color: #dc2626;
  font-weight: 700;
  border-radius: 6px;
}

.final-line {
  margin-top: 1.4rem;
  font-size: 1.45rem;
  font-weight: 700;
}

.highlight-warn { color: #dc2626; }
.highlight-ok { color: #059669; }
</style>


