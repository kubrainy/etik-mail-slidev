<template>
  <div class="slide-root">
    <div class="stage-area">
      <div class="stat-stage" v-click.hide="3">
        <div class="hero-number" v-click="1">
          30 <span class="hero-sub">unseen samples</span>
        </div>

        <div class="cat-row" v-click="2">
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
      </div>

      <div class="result-stage" v-click="3">
        <div class="result-row">
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
                  <th>Etik Değil</th>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <th rowspan="2" class="matrix-side">Gerçek</th>
                  <th>Etik</th>
                  <td class="cell-ok">17</td>
                  <td class="cell-warn">3</td>
                </tr>
                <tr>
                  <th>Etik Değil</th>
                  <td class="cell-zero">0</td>
                  <td class="cell-ok">10</td>
                </tr>
              </tbody>
            </table>
          </div>

          <div class="score-block">
            <div class="score-pct">%90</div>
            <div class="score-frac">27 / 30 doğru</div>
            <div class="pasif-badge" v-click="4">Pasif-agresif: 10/10 ✓</div>
          </div>
        </div>

        <div class="limitation" v-click="5">
          Sert ama profesyonel iletişim ile etik dışı iletişim arasındaki
          sınırda, model zaman zaman <span class="highlight-warn">aşırı hassas</span>
          davranabiliyor
          <span class="limitation-detail">(20 örnekten 3'ü yanlış etiketlendi)</span>.
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.slide-root {
  width: 100vh;
  height: 100%;
  min-height: 460px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.stage-area {
  position: relative;
  width: 100%;
  min-height: 420px;
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

.hero-number {
  font-size: 4rem;
  font-weight: 800;
  color: #7c3aed;
  line-height: 1;
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
  flex-wrap: nowrap;
  justify-content: center;
  gap: 1rem;
  margin-top: 1.4rem;
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

.result-stage {
  position: absolute;
  inset: 0;
  margin: auto;
  width: fit-content;
  height: fit-content;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1.3rem;
  text-align: center;
}

.result-row {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 3rem;
}

.corner {
  border: none;
}

.matrix-side {
  writing-mode: vertical-rl;
  transform: rotate(180deg);
  font-weight: 700;
  opacity: 0.75;
  font-size: 1rem;
  padding: 0.6rem 0.4rem;
  border-right: 1px solid rgba(120, 120, 120, 0.25);
}

.matrix {
  border-collapse: collapse;
  font-size: 1.15rem;
}

.matrix th, .matrix td {
  padding: 0.55rem 1.2rem;
  text-align: center;
}

.matrix thead th {
  font-weight: 700;
  opacity: 0.7;
  font-size: 0.95rem;
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

.score-block {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.6rem;
  min-width: 150px;
}

.score-pct {
  font-size: 3rem;
  font-weight: 800;
  color: #059669;
  line-height: 1;
}

.score-frac {
  font-size: 1.1rem;
  font-weight: 700;
  opacity: 0.75;
}

.pasif-badge {
  margin-top: 0.4rem;
  padding: 0.5rem 1.4rem;
  border-radius: 999px;
  background: rgba(5, 150, 105, 0.1);
  border: 1px solid rgba(5, 150, 105, 0.35);
  color: #059669;
  font-weight: 700;
  font-size: 0.95rem;
}

.limitation {
  max-width: 700px;
  padding: 1rem 1.6rem;
  border-radius: 12px;
  background: rgba(220, 38, 38, 0.06);
  border: 1px solid rgba(220, 38, 38, 0.25);
  font-size: 1.05rem;
  line-height: 1.5;
}

.highlight-warn {
  color: #dc2626;
  font-weight: 700;
}

.limitation-detail {
  opacity: 0.6;
  font-size: 0.9rem;
}
</style>