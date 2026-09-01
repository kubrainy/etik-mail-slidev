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

    <div class="results-area" v-click="1">
      <div class="metrics-grid">
        <div class="metric-card">
          <div class="metric-label">Accuracy</div>
          <div class="metric-value">99.845%</div>
        </div>
        <div class="metric-card">
          <div class="metric-label">Precision</div>
          <div class="metric-value">100%</div>
        </div>
        <div class="metric-card">
          <div class="metric-label">Recall</div>
          <div class="metric-value">99.690%</div>
        </div>
        <div class="metric-card">
          <div class="metric-label">F1</div>
          <div class="metric-value">99.845%</div>
        </div>
      </div>
      <div class="metrics-note">645 örnek</div>

      <v-click>
        <div class="matrix-wrap">
          <table class="matrix">
            <thead>
              <tr>
                <th></th>
                <th colspan="2">Tahmin</th>
              </tr>
              <tr>
                <th></th>
                <th>Etik</th>
                <th>Etik Dışı</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <th>Gerçek Etik</th>
                <td class="cell-ok">322</td>
                <td class="cell-zero">0</td>
              </tr>
              <tr>
                <th>Gerçek Etik Dışı</th>
                <td class="cell-warn">1</td>
                <td class="cell-ok">322</td>
              </tr>
            </tbody>
          </table>
        </div>
      </v-click>

      <v-click>
        <div class="final-line">
          Yalnızca <span class="highlight-warn">1 yanlış negatif</span> ·
          <span class="highlight-ok">0 yanlış pozitif</span>
        </div>
      </v-click>
    </div>
  </div>
</template>

<style scoped>
.stage-area {
  position: relative;
  min-height: 400px;
  margin-top: 1rem;
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

.results-area {
  position: absolute;
  inset: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin-top: 2rem;
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
  font-size: 0.95rem;
  opacity: 0.6;
  font-weight: 600;
  letter-spacing: 0.05em;
}

.metric-value {
  font-size: 2.4rem;
  font-weight: 800;
  color: #7c3aed;
  line-height: 1.1;
}

.metrics-note {
  margin-top: 0.6rem;
  font-size: 0.9rem;
  opacity: 0.5;
  font-style: italic;
}

.matrix-wrap {
  margin-top: 1.6rem;
}

.matrix {
  border-collapse: collapse;
  font-size: 0.95rem;
}

.matrix th, .matrix td {
  padding: 0.45rem 1rem;
  text-align: center;
}

.matrix thead th {
  font-weight: 700;
  opacity: 0.7;
  font-size: 0.85rem;
}

.matrix tbody th {
  font-weight: 700;
  opacity: 0.75;
  text-align: right;
  padding-right: 1rem;
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
  font-size: 1.25rem;
  font-weight: 700;
}

.highlight-warn { color: #dc2626; }
.highlight-ok { color: #059669; }
</style>