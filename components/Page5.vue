<template>
  <div class="dataset-slide">
    <div class="number-stage">
      <div class="big-number">3.222</div>
      <div class="subtitle">benzersiz Türkçe metin</div>
    </div>

    <v-click>
      <div class="classes-row">
        <div class="class-box class-ethical">
          <span class="class-num">1</span> Etik
        </div>
        <div class="class-box class-unethical">
          <span class="class-num">0</span> Etik Dışı
        </div>
      </div>
    </v-click>

    <v-click>
      <div class="subcat-box">
        <span class="subcat-pill">Hiyerarşik baskı</span>
        <span class="subcat-pill">Küçümseyici ifadeler</span>
        <span class="subcat-pill">Pasif-agresif söylem</span>
        <span class="subcat-pill">Tehditkâr dil</span>
        <span class="subcat-pill">Mobbing</span>
      </div>
    </v-click>

    <div class="model-qr">
      <img src="/model-qr.png" alt="Modeli incelemek için QR kodu" />
      <span class="model-qr-text">
        <span class="model-qr-label">Eğitilmiş Veri Seti Modelini İncele</span>
      </span>
    </div>
  </div>
</template>

<style scoped>
.dataset-slide {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.number-stage {
  text-align: center;
  margin-top: 0.5rem;
}

.big-number {
  font-size: 5.6rem;
  font-weight: 800;
  color: #7c3aed;
  line-height: 1;
  letter-spacing: -0.02em;
}

.subtitle {
  font-size: 1.25rem;
  opacity: 0.7;
  margin-top: 0.3rem;
}

.classes-row {
  display: flex;
  justify-content: center;
  gap: 2rem;
  margin-top: 2rem;
}

.class-box {
  padding: 0.85rem 2.2rem;
  border-radius: 12px;
  font-size: 1.25rem;
  font-weight: 700;
  min-width: 190px;
  text-align: center;
}

.class-num {
  display: inline-block;
  width: 1.6rem;
  height: 1.6rem;
  border-radius: 50%;
  font-size: 0.9rem;
  line-height: 1.6rem;
  margin-right: 0.5rem;
  background: rgba(255, 255, 255, 0.25);
}

.class-ethical {
  background: rgba(16, 185, 129, 0.12);
  border: 1px solid rgba(16, 185, 129, 0.4);
  color: #059669;
}

.class-unethical {
  background: rgba(220, 38, 38, 0.1);
  border: 1px solid rgba(220, 38, 38, 0.35);
  color: #dc2626;
}

.subcat-box {
  display: flex;
  justify-content: center;
  gap: 0.7rem;
  flex-wrap: wrap;
  max-width: 760px;
  margin: 1.6rem auto 0;
}

.subcat-pill {
  padding: 0.5rem 1.2rem;
  border-radius: 999px;
  background: rgba(220, 38, 38, 0.08);
  border: 1px solid rgba(220, 38, 38, 0.3);
  color: #dc2626;
  font-size: 0.95rem;
  font-weight: 600;
}

.model-qr {
  display: inline-flex;
  align-items: center;
  gap: 0.9rem;
  margin-top: 2rem;
  padding: 0.7rem 1.1rem;
  border-radius: 14px;
  background: rgba(124, 58, 237, 0.06);
  border: 1px solid rgba(124, 58, 237, 0.25);
  text-decoration: none;
  color: inherit;
}

.model-qr img {
  width: 92px;
  height: 92px;
  border-radius: 8px;
  background: white;
  padding: 5px;
}

.model-qr-text {
  font-size: 0.8rem;
  line-height: 1.45;
  opacity: 0.65;
  text-align: left;
  max-width: 220px;
  word-break: break-all;
}

.model-qr-label {
  display: block;
  font-size: 0.9rem;
  font-weight: 700;
  color: #7c3aed;
  opacity: 1;
  margin-bottom: 0.2rem;
  word-break: normal;
}
</style>
