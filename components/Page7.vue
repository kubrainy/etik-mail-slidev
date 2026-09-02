<template>
  <div class="tech-box">
    <div class="tech-title">BertForSequenceClassification</div>
    <div class="tech-row"><span>Learning Rate</span><span>2×10⁻⁵</span></div>
    <div class="tech-row"><span>Batch Size</span><span>8</span></div>
    <div class="tech-row"><span>Epochs</span><span>5</span></div>
    <div class="tech-row"><span>Optimizer</span><span>AdamW</span></div>
  </div>

  <div class="stage">
    <div class="hero-model">BERTürk</div>
    <div class="hero-line" />

    <div class="branches" v-click="1">
      <div class="branch">
        <div class="branch-icon">🇹🇷</div>
        <div class="branch-label">Türkçe için önceden eğitilmiş BERT modeli</div>
      </div>
      <div class="branch">
        <div class="branch-icon">🎯</div>
        <div class="branch-label">Etik / etik dışı sınıflandırma için <b>fine-tune</b> edildi</div>
      </div>
    </div>

    <div class="contrast" v-click="2">
      <div class="contrast-item contrast-dim">
        <s>Sadece belirli kelimeleri arama</s>
      </div>
      <div class="contrast-arrow">→</div>
      <div class="contrast-item contrast-highlight">
        Metni <b>bağlamsal</b> olarak değerlendirebilme
      </div>
    </div>
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

.stage {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 2.5rem;
  gap: 0;
}

.hero-model {
  padding: 0.9rem 2.6rem;
  border-radius: 12px;
  background: #7c3aed;
  color: white;
  font-size: 1.5rem;
  font-weight: 800;
  letter-spacing: 0.01em;
}

.hero-line {
  width: 1px;
  height: 28px;
  background: rgba(124, 58, 237, 0.4);
}

.branches {
  display: flex;
  gap: 2.5rem;
  margin-top: 0.4rem;
}

.branch {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.5rem;
  width: 240px;
  padding: 1rem 1.2rem;
  border-radius: 12px;
  background: rgba(124, 58, 237, 0.06);
  border: 1px solid rgba(124, 58, 237, 0.22);
  text-align: center;
}

.branch-icon {
  font-size: 1.4rem;
}

.branch-label {
  font-size: 0.98rem;
  line-height: 1.4;
  opacity: 0.85;
}

.branch-label b {
  color: #7c3aed;
  opacity: 1;
}

.contrast {
  display: flex;
  align-items: center;
  gap: 1.2rem;
  margin-top: 2.2rem;
  padding: 1rem 1.6rem;
  border-radius: 14px;
  background: rgba(124, 58, 237, 0.1);
  border: 1px solid rgba(124, 58, 237, 0.3);
}

.contrast-item {
  font-size: 1.05rem;
  font-weight: 600;
  text-align: center;
}

.contrast-dim {
  opacity: 0.4;
  font-weight: 400;
}

.contrast-arrow {
  font-size: 1.2rem;
  color: #7c3aed;
  opacity: 0.6;
}

.contrast-highlight {
  color: #7c3aed;
}
</style>