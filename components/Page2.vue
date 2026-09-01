<template>
  <div class="stage-wrap">
    <v-click>
      <div class="flow-col">
        <div class="flow-item">Geleneksel iletişim</div>
        <div class="arrow">↓</div>
        <div class="flow-item">Dijital iletişim</div>
        <div class="arrow">↓</div>
        <div class="flow-item flow-final">
          E-posta / Mesajlaşma /<br>Proje Yönetim Platformları
        </div>
      </div>
    </v-click>

    <v-click>
      <div class="tag-col">
        <span class="pill">Hız</span>
        <span class="pill">Verimlilik</span>
        <span class="pill">Uzaktan çalışma</span>
        <span class="pill">Hibrit çalışma</span>
      </div>
    </v-click>
  </div>

  <v-click>
    <div class="punchline mt-10">
      İletişim dijitalleştikçe, <span class="highlight">etik dışı iletişim</span>
      de dijital kanallara taşınıyor.
    </div>
  </v-click>
</template>

<style scoped>
.stage-wrap {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 4rem;
  margin-top: 3.5rem;
  flex-wrap: wrap;
}

.flow-col {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.3rem;
}

.flow-item {
  padding: 0.7rem 1.6rem;
  border-radius: 10px;
  background: rgba(124, 58, 237, 0.07);
  border: 1px solid rgba(124, 58, 237, 0.25);
  font-size: 1.15rem;
  min-width: 260px;
  text-align: center;
}

.flow-final {
  background: rgba(124, 58, 237, 0.12);
  border-color: rgba(124, 58, 237, 0.45);
  font-weight: 700;
  color: #7c3aed;
  line-height: 1.4;
}

.arrow {
  font-size: 1.4rem;
  color: #7c3aed;
  opacity: 0.6;
}

.tag-col {
  display: flex;
  flex-direction: column;
  gap: 0.8rem;
}

.pill {
  padding: 0.55rem 1.6rem;
  border-radius: 999px;
  background: rgba(124, 58, 237, 0.1);
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
  border: 1px solid rgba(124, 58, 237, 0.3);
  color: #7c3aed;
  font-weight: 600;
  font-size: 1.05rem;
  text-align: center;
}

.punchline {
  font-size: 1.6rem;
  font-weight: 700;
  max-width: 780px;
  margin: 0 auto;
  margin-top: 2rem;
  line-height: 1.5;
  text-align: center;
}

.highlight {
  color: #7c3aed;
}
</style>