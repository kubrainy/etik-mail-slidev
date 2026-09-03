<template>
  <div class="lit-title">LİTERATÜR</div>

  <div class="lit-table">
    <div class="lit-row">
      <div class="lit-domain">Sosyal medya</div>
      <div class="lit-arrow">→</div>
      <div class="lit-focus">Toksik / saldırgan dil</div>
      <div class="lit-arrow">→</div>
      <div class="lit-q">"Zararlı mı?"</div>
    </div>

    <div class="lit-row">
      <div class="lit-domain">Kurumsal e-posta + NLP</div>
      <div class="lit-arrow">→</div>
      <div class="lit-focus">Phishing / fraud / spam / insider threat / konu</div>
      <div class="lit-arrow">→</div>
      <div class="lit-q">"Güvenlik veya içerik kategorisi ne?"</div>
    </div>

    <v-click>
      <div class="lit-row lit-row--ours">
        <div class="lit-domain">Kurumsal iletişim + etik</div>
        <div class="lit-arrow">→</div>
        <div class="lit-focus">Güven / şeffaflık / kontrol / etik algı</div>
        <div class="lit-arrow">→</div>
        <div class="lit-q">"Bu iletişim davranışı nasıl algılanıyor?"</div>
      </div>
    </v-click>
  </div>

  <div class="punchline-slot">
    <v-click>
      <div class="punchline">
        Yani bizim sorumuz <s class="dim">"Bu e-posta dolandırıcılık mı?"</s> değil;<br>
        <span class="highlight">"Bu e-posta çalışanlar arası etik iletişime uygun mu?"</span>
      </div>
    </v-click>
  </div>
</template>

<style scoped>
.lit-title {
  text-align: center;
  font-size: 2rem;
  letter-spacing: 0.12em;
  opacity: 0.5;
  font-weight: 600;
  margin-top: 1rem;
}

.lit-table {
  margin: 2rem auto 0;
  max-width: 900px;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.lit-row {
  display: grid;
  grid-template-columns: 1fr auto 1.3fr auto 1.2fr;
  align-items: center;
  gap: 0.8rem;
  padding: 1rem 1.4rem;
  border-radius: 14px;
  background: rgba(128, 128, 128, 0.07);
  border: 1px solid rgba(128, 128, 128, 0.2);
}

.lit-row--ours {
  background: rgba(124, 58, 237, 0.12);
  border: 1px solid rgba(124, 58, 237, 0.45);
  box-shadow: 0 0 40px rgba(124, 58, 237, 0.2);
}

.lit-domain {
  font-weight: 700;
  font-size: 1.05rem;
}

.lit-arrow {
  opacity: 0.4;
  font-size: 1.1rem;
}

.lit-focus {
  font-size: 0.95rem;
  opacity: 0.8;
}

.lit-q {
  font-size: 0.98rem;
  font-style: italic;
  font-weight: 600;
}

.lit-row--ours .lit-q {
  color: #a78bfa;
}

.punchline-slot {
  min-height: 90px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-top: 1.5rem;
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
