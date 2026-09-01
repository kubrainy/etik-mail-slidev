<template>
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
        <span class="class-num">2</span> Etik Dışı
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
</template>

<style scoped>
.number-stage {
  text-align: center;
  margin-top: 1.5rem;
}

.big-number {
  font-size: 6rem;
  font-weight: 800;
  color: #7c3aed;
  line-height: 1;
  letter-spacing: -0.02em;
}

.subtitle {
  font-size: 1.3rem;
  opacity: 0.7;
  margin-top: 0.3rem;
}

.classes-row {
  display: flex;
  justify-content: center;
  gap: 2rem;
  margin-top: 2.5rem;
}

.class-box {
  padding: 0.9rem 2.4rem;
  border-radius: 12px;
  font-size: 1.3rem;
  font-weight: 700;
  min-width: 200px;
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
  max-width: 780px;
  margin: 2rem auto 0;
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
</style>