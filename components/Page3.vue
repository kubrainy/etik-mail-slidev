<template>
  <div class="known-title">MEVCUT ÇALIŞMALAR</div>

  <div class="stage">
    <div class="compare-wrap" v-click.hide="1">
      <div class="col col-known">
        <div class="col-title">Sosyal Medya</div>
        <div class="item">Hakaret</div>
        <div class="item">Küfür</div>
        <div class="item">Nefret söylemi</div>
        <div class="item">Siber zorbalık</div>
      </div>

      <div class="divider" />

      <div class="col col-known">
        <div class="col-title">Kurumsal E-posta</div>
        <div class="item item-q">?</div>
        <div class="item item-q">?</div>
        <div class="item item-q">?</div>
        <div class="item item-q">?</div>
      </div>
    </div>

    <div class="gap-box" v-click="1">
      <div class="gap-title">LİTERATÜRDEKİ BOŞLUK</div>
      <div class="gap-items">
        <span class="gap-pill">Örtük dil</span>
        <span class="gap-pill">Pasif-agresif dil</span>
        <span class="gap-pill">Hiyerarşik baskı</span>
        <span class="gap-pill">Dijital mobbing</span>
      </div>
    </div>
  </div>

  <div class="punchline-slot">
    <div class="punchline" v-click="2">
      Yani bizim sorumuz <s class="dim">"Bu e-posta dolandırıcılık mı?"</s> değil;<br>
      <span class="highlight">"Bu e-posta çalışanlar arası etik iletişime uygun mu?"</span>
    </div>
  </div>
</template>

<style scoped>
.known-title {
  text-align: center;
  font-size: 1rem;
  letter-spacing: 0.12em;
  opacity: 0.5;
  font-weight: 600;
  margin-top: 1rem;
}

.stage {
  position: relative;
  height: 300px;
  margin-top: 1.5rem;
}

.compare-wrap {
  position: absolute;
  inset: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 2.5rem;
}

.divider {
  width: 1px;
  align-self: stretch;
  background: rgba(120, 120, 120, 0.25);
}

.col {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  min-width: 220px;
}

.col-title {
  font-weight: 700;
  font-size: 1.15rem;
  text-align: center;
  margin-bottom: 0.3rem;
  opacity: 0.75;
}

.item {
  padding: 0.5rem 1rem;
  border-radius: 8px;
  background: rgba(120, 120, 120, 0.08);
  text-align: center;
  font-size: 1rem;
  opacity: 0.7;
}

.item-q {
  font-weight: 700;
  font-size: 1.2rem;
  color: #7c3aed;
  background: rgba(124, 58, 237, 0.08);
  opacity: 1;
}

.gap-box {
  position: absolute;
  inset: 0;
  margin: auto;
  width: fit-content;
  height: fit-content;
  max-width: 640px;
  padding: 2rem 2.4rem;
  border-radius: 16px;
  background: rgba(124, 58, 237, 0.1);
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
  border: 1px solid rgba(124, 58, 237, 0.35);
  text-align: center;
}

.gap-title {
  font-weight: 800;
  font-size: 1.3rem;
  letter-spacing: 0.08em;
  color: #7c3aed;
  margin-bottom: 1.2rem;
}

.gap-items {
  display: flex;
  gap: 0.8rem;
  justify-content: center;
  flex-wrap: wrap;
}

.gap-pill {
  padding: 0.6rem 1.4rem ;
  border-radius: 999px;
  background: #7c3aed;
  color: white;
  font-weight: 600;
  font-size: 1.05rem;
}

.punchline-slot {
  min-height: 90px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-top: 1rem;
}

.punchline {
  font-size: 1.5rem;
  font-weight: 700;
  max-width: 780px;
  line-height: 1.55;
  text-align: center;
}

.dim {
  opacity: 0.45;
  font-weight: 400;
  font-size: 1.2rem;
}

.highlight {
  color: #7c3aed;
}
</style>