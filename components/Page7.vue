<template>
  <div class="tech-box">
    <div class="tech-title">BertForSequenceClassification</div>
    <div class="tech-row"><span>Learning Rate</span><span>2×10⁻⁵</span></div>
    <div class="tech-row"><span>Batch Size</span><span>8</span></div>
    <div class="tech-row"><span>Epochs</span><span>5</span></div>
    <div class="tech-row"><span>Optimizer</span><span>AdamW</span></div>
  </div>

  <div class="columns">
    <v-click>
      <div class="col">
        <div class="node">Türkçe</div>
        <div class="arrow">↓</div>
        <div class="node node-model">BERTürk</div>
        <div class="arrow">↓</div>
        <div class="node">Bağlamsal Temsil</div>
      </div>
    </v-click>

    <div class="col-divider" />

    <v-click>
      <div class="col">
        <div class="node">Önceden Eğitilmiş</div>
        <div class="arrow">↓</div>
        <div class="node node-model">Fine-tuning</div>
        <div class="arrow">↓</div>
        <div class="node node-final">Etik / Etik Dışı</div>
      </div>
    </v-click>
  </div>
</template>

<style scoped>
.tech-box {
  position: absolute;
  top: 5.5rem;
  right: 4%;
  padding: 0.7rem 1rem;
  border-radius: 10px;
  background: rgba(120, 120, 120, 0.06);
  border: 1px solid rgba(120, 120, 120, 0.2);
  font-size: 0.7rem;
  opacity: 0.6;
  min-width: 150px;
}

.tech-title {
  font-weight: 700;
  font-size: 0.65rem;
  margin-bottom: 0.4rem;
  opacity: 0.8;
  letter-spacing: 0.02em;
}

.tech-row {
  display: flex;
  justify-content: space-between;
  gap: 0.8rem;
  padding: 0.1rem 0;
}

.columns {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 3rem;
  margin-top: 2.5rem;
}

.col {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.col-divider {
  width: 1px;
  height: 180px;
  background: rgba(120, 120, 120, 0.2);
}

.node {
  padding: 0.7rem 1.8rem;
  border-radius: 10px;
  background: rgba(124, 58, 237, 0.06);
  border: 1px solid rgba(124, 58, 237, 0.2);
  font-size: 1.05rem;
  font-weight: 600;
  min-width: 220px;
  text-align: center;
}

.node-model {
  background: rgba(124, 58, 237, 0.14);
  border-color: rgba(124, 58, 237, 0.45);
  color: #7c3aed;
  font-size: 1.2rem;
  font-weight: 800;
}

.node-final {
  background: #7c3aed;
  border-color: #7c3aed;
  color: white;
}

.arrow {
  font-size: 1.2rem;
  color: #7c3aed;
  opacity: 0.5;
  line-height: 1.4;
}
</style>