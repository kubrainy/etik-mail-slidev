<template>
  <div class="compare-wrap">
    <div class="col">
      <div class="col-title">Yüz Yüze İletişim</div>
      <div class="col-items">
        <div class="item">Ses tonu</div>
        <div class="item">Beden dili</div>
        <div class="item">Mimik</div>
      </div>
      <div class="arrow">↓</div>
      <div class="col-result">"Nasıl söyledi?"</div>
    </div>

    <div class="col-divider" />

    <div class="col">
      <div class="col-title">E-posta</div>
      <div class="col-items">
        <div class="item item-empty">—</div>
        <div class="item item-empty">—</div>
        <div class="item item-empty">—</div>
      </div>
      <div class="arrow">↓</div>
      <div class="col-result col-result-final">"Ne yazdı?"</div>
    </div>
  </div>

  <v-click>
    <div class="question">
      Peki bu kelimeler etik dışı olduğunda bunu <u>insan gözüyle</u> mi,
      <span class="highlight">yapay zekâyla</span> mı tespit edeceğiz?
    </div>
  </v-click>
</template>

<style scoped>
.compare-wrap {
  display: flex;
  align-items: flex-start;
  justify-content: center;
  gap: 3rem;
  margin-top: 2rem;
}

.col {
  display: flex;
  flex-direction: column;
  align-items: center;
  min-width: 220px;
}

.col-title {
  font-weight: 700;
  font-size: 1.2rem;
  margin-bottom: 1rem;
  opacity: 0.85;
}

.col-items {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  width: 100%;
}

.item {
  padding: 0.5rem 1rem;
  border-radius: 8px;
  background: rgba(124, 58, 237, 0.06);
  border: 1px solid rgba(124, 58, 237, 0.2);
  text-align: center;
  font-size: 0.95rem;
}

.item-empty {
  opacity: 1;
  background: rgba(146, 146, 146, 0.123);
  border-color: rgba(94, 93, 93, 0.212);
}

.arrow {
  font-size: 1.3rem;
  color: #7c3aed;
  opacity: 0.5;
  margin: 0.6rem 0;
}

.col-result {
  font-size: 1.1rem;
  font-weight: 700;
  font-style: italic;
  opacity: 0.75;
}

.col-result-final {
  color: #7c3aed;
  opacity: 1;
}

.col-divider {
  width: 1px;
  align-self: stretch;
  background: rgba(120, 120, 120, 0.2);
}

.question {
  font-size: 1.2rem;
  font-weight: 600;
  max-width: 680px;
  margin: 1.8rem auto 0;
  padding-top: 1.5rem;
  border-top: 1px solid rgba(120, 120, 120, 0.2);
  line-height: 1.55;
  text-align: center;
  opacity: 0.9;
}

.highlight {
  color: #7c3aed;
}

:deep(.slidev-vclick-target) {
  transition: opacity 0.7s cubic-bezier(0.16, 1, 0.3, 1),
    transform 0.7s cubic-bezier(0.16, 1, 0.3, 1);
}

:deep(.slidev-vclick-hidden) {
  opacity: 0;
  transform: translateY(14px);
}
</style>