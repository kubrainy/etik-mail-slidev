<template>
  <div class="known-title" v-click.hide="1">MEVCUT ÇALIŞMALAR</div>

  <div class="stage">
    <div class="spotlights" v-click.hide="1">
      <div class="spot">
        <div class="spot-beam spot-beam-red" />
        <div class="spot-label">Sosyal Medya</div>
        <div class="spot-tags">
          <div class="tag tag-red">Hakaret</div>
          <div class="tag tag-red">Küfür</div>
          <div class="tag tag-red">Nefret Söylemi</div>
          <div class="tag tag-red">Siber Zorbalık</div>
        </div>
      </div>

      <div class="dark-gap">
        <div class="gap-mark">?</div>
      </div>

      <div class="spot">
        <div class="spot-beam spot-beam-amber" />
        <div class="spot-label">Kurumsal E-posta</div>
        <div class="spot-tags">
          <div class="tag tag-amber">Dolandırıcılık</div>
          <div class="tag tag-amber">Phishing</div>
          <div class="tag tag-amber">Insider Threat</div>
        </div>
      </div>
    </div>

    <div class="reveal-box" v-click="1">
      <div class="reveal-title">LİTERATÜRDEKİ BOŞLUK</div>
      <div class="reveal-items">
        <span class="reveal-pill">Örtük dil</span>
        <span class="reveal-pill">Pasif-agresif dil</span>
        <span class="reveal-pill">Hiyerarşik baskı</span>
        <span class="reveal-pill">Dijital mobbing</span>
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
  font-size: 2rem;
  letter-spacing: 0.12em;
  opacity: 0.5;
  font-weight: 600;
  margin-top: 1rem;
}

.stage {
  position: relative;
  height: 320px;
  margin-top: 1.5rem;
  border-radius: 20px;
  background: rgba(128, 128, 128, 0.06);
  border: 1px solid rgba(128, 128, 128, 0.18);
  overflow: hidden;
}

.spotlights {
  position: absolute;
  inset: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0;
}

.spot {
  position: relative;
  width: 260px;
  padding: 2rem 1rem 1.5rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.5rem;
}

.spot-beam {
  position: absolute;
  top: -20px;
  left: 50%;
  transform: translateX(-50%);
  width: 220px;
  height: 260px;
  clip-path: polygon(46% 0%, 54% 0%, 100% 100%, 0% 100%);
  pointer-events: none;
}

.spot-beam-red {
  background: linear-gradient(180deg, rgba(239, 68, 68, 0.16), transparent 75%);
}

.spot-beam-amber {
  background: linear-gradient(180deg, rgba(245, 158, 11, 0.16), transparent 75%);
}

.spot-label {
  position: relative;
  font-weight: 700;
  font-size: 1.1rem;
  color: inherit;
  opacity: 0.9;
}

.spot-tags {
  position: relative;
  display: flex;
  flex-direction: column;
  gap: 0.4rem;
  width: 100%;
}

.tag {
  position: static;
  padding: 0.4rem 0.8rem;
  border-radius: 8px;
  text-align: center;
  font-size: 0.92rem;
  color: inherit;
  opacity: 0.8;
  background: rgba(128, 128, 128, 0.08);
}

.tag-red { border: 1px solid rgba(239, 68, 68, 0.4); }
.tag-amber { border: 1px solid rgba(245, 158, 11, 0.4); }

.dark-gap {
  width: 140px;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.gap-mark {
  font-size: 2.4rem;
  font-weight: 800;
  color: currentColor;
  opacity: 0.2;
  animation: pulse-q 2.4s ease-in-out infinite;
}

@keyframes pulse-q {
  0%, 100% { opacity: 0.2; transform: scale(1); }
  50% { opacity: 0.5; transform: scale(1.15); }
}

.reveal-box {
  position: absolute;
  inset: 0;
  margin: auto;
  width: fit-content;
  height: fit-content;
  max-width: 620px;
  padding: 2rem 2.4rem;
  border-radius: 16px;
  background: rgba(124, 58, 237, 0.12);
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
  border: 1px solid rgba(124, 58, 237, 0.45);
  text-align: center;
  box-shadow: 0 0 60px rgba(124, 58, 237, 0.25);
}

.reveal-title {
  font-weight: 800;
  font-size: 1.3rem;
  letter-spacing: 0.08em;
  color: #a78bfa;
  margin-bottom: 1.2rem;
}

.reveal-items {
  display: flex;
  gap: 0.8rem;
  justify-content: center;
  flex-wrap: wrap;
}

.reveal-pill {
  padding: 0.6rem 1.4rem;
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