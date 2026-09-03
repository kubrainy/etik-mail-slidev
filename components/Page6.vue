<script setup>
import { computed } from 'vue'
import { useSlideContext } from '@slidev/client'

const { $clicks } = useSlideContext()
const clicks = computed(() => Math.min($clicks?.value ?? 0, 3))

const SRC = {
  claude: { x: 46, y: 62 },
  gpt: { x: 46, y: 196 },
}

const mails = [
  { id: 1, from: 'claude' },
  { id: 2, from: 'claude' },
  { id: 3, from: 'claude' },
  { id: 4, from: 'gpt' },
  { id: 5, from: 'gpt' },
  { id: 6, from: 'gpt' },
].map((m, k) => {
  const s = SRC[m.from]
  const hub = { x: 400 + (k % 2 ? 7 : -7), y: 96 + k * 11 }  
  const ds = { x: 812, y: 70 + k * 30 }                      
  return {
    ...m,
    k,
    style: {
      left: `${s.x}px`,
      top: `${s.y}px`,
      '--i': k,
      '--hx': `${hub.x - s.x}px`,
      '--hy': `${hub.y - s.y}px`,
      '--dx': `${ds.x - s.x}px`,
      '--dy': `${ds.y - s.y}px`,
    },
  }
})

const captions = [
  'Metinler nasıl oluşturuldu?',
  "BDM'ler aday e-posta metinleri üretir",
  'Her metin tek tek okunur, kontrol edilir ve etiketlenir',
  'Yalnızca insan onayından geçen metinler veri setine girer',
]
</script>

<template>
  <div class="wrap">
    <div class="scene" :class="`phase-${clicks}`">
      <div class="track" />

      <div class="src src-claude">
        <div class="emblem">
          <svg viewBox="0 0 24 24" class="mk">
            <g stroke="#fff" stroke-width="3" stroke-linecap="round">
              <line x1="12" y1="3.5" x2="12" y2="20.5" />
              <line x1="4.6" y1="7.75" x2="19.4" y2="16.25" />
              <line x1="4.6" y1="16.25" x2="19.4" y2="7.75" />
            </g>
          </svg>
        </div>
        <div class="src-name">Claude</div>
      </div>
      <div class="src src-gpt">
        <div class="emblem">
          <svg viewBox="0 0 24 24" class="mk">
            <path d="M12 3.2 20 7.6v8.8L12 20.8 4 16.4V7.6z" fill="none" stroke="#fff" stroke-width="2.6" stroke-linejoin="round" />
            <circle cx="12" cy="12" r="2.4" fill="#fff" />
          </svg>
        </div>
        <div class="src-name">ChatGPT</div>
      </div>

      <div class="human">
        <div class="human-label">İnsan İncelemesi</div>
        <div class="human-fig">
          <span class="person">🧑‍💻</span>
          <span class="lens">🔍</span>
        </div>
        <div class="human-sub">doğallık · bağlam · tekrar · etiketleme</div>
      </div>

      <div class="dataset">
        <div class="ds-box">
          <div class="ds-fill" />
          <div class="ds-lines">
            <span v-for="n in 6" :key="n" />
          </div>
          <div class="ds-count">
            <span class="ds-num">3.222</span>
            <span class="ds-unit">metin</span>
          </div>
        </div>
        <div class="ds-label">Veri Seti</div>
        <div class="ds-sub">hazır küme</div>
      </div>

      <div class="mail-layer">
        <div
          v-for="m in mails"
          :key="m.id"
          class="mail"
          :class="`from-${m.from}`"
          :style="m.style"
        >
          <span class="mail-ico">✉️</span>
          <span class="mail-check">✓</span>
        </div>
      </div>
    </div>

    <div class="caption" :class="`cap-${clicks}`">
      {{ captions[clicks] }}
    </div>
  </div>
</template>

<style scoped>
.wrap {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1.4rem;
  margin-top: 0.5rem;
}

.scene {
  position: relative;
  width: 940px;
  height: 340px;
  max-width: 96vw;
  flex-shrink: 0;
}

.track {
  position: absolute;
  left: 130px;
  right: 130px;
  top: 150px;
  border-top: 2px dashed rgba(124, 58, 237, 0.28);
  z-index: 0;
}

.src {
  position: absolute;
  left: 0;
  width: 132px;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.4rem;
  z-index: 2;
  transition: transform 0.4s ease, filter 0.4s ease;
}
.src-claude { top: 34px; }
.src-gpt { top: 168px; }

.emblem {
  width: 66px;
  height: 66px;
  border-radius: 20px;
  display: grid;
  place-items: center;
  box-shadow: 0 10px 24px rgba(0, 0, 0, 0.18);
}
.mk {
  width: 36px;
  height: 36px;
}
.src-claude .emblem { background: linear-gradient(135deg, #d97757, #bf5230); }
.src-gpt .emblem { background: linear-gradient(135deg, #10a37f, #0c7f62); }

.src-name {
  font-size: 0.95rem;
  font-weight: 700;
  opacity: 0.8;
}

.phase-1 .src { transform: translateY(-2px); }
.phase-1 .src .emblem { animation: pulse 1.4s ease-in-out infinite; }


.human {
  position: absolute;
  left: 290px;
  top: 6px;
  width: 260px;
  text-align: center;
  z-index: 3;
}
.human-fig {
  position: relative;
  height: 128px;
  display: grid;
  place-items: center;
}
.person {
  font-size: 84px;
  line-height: 1;
  filter: grayscale(0.15);
  transition: transform 0.4s ease;
}
.lens {
  position: absolute;
  right: 62px;
  top: 30px;
  font-size: 38px;
  opacity: 0;
  transition: opacity 0.4s ease;
}
.human-label {
  font-weight: 800;
  color: #7c3aed;
  font-size: 1.1rem;
  margin-bottom: 0.35rem;
}
.human-sub {
  font-size: 0.82rem;
  opacity: 0.6;
  margin-top: 0.35rem;
}

.phase-2 .person { transform: scale(1.05); }
.phase-1 .lens,
.phase-2 .lens { opacity: 1; animation: scan 1.6s ease-in-out infinite; }

.dataset {
  position: absolute;
  right: 0;
  top: 26px;
  width: 150px;
  text-align: center;
}
.ds-box {
  position: relative;
  height: 210px;
  border-radius: 16px;
  border: 2px solid rgba(124, 58, 237, 0.4);
  background: rgba(124, 58, 237, 0.06);
  overflow: hidden;
  transition: box-shadow 0.5s ease, border-color 0.5s ease;
}
.ds-fill {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
  height: 0;
  background: linear-gradient(180deg, rgba(124, 58, 237, 0.35), rgba(124, 58, 237, 0.15));
}
.ds-lines {
  position: absolute;
  inset: 18px 16px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 10px;
  transition: opacity 0.4s ease;
}
.ds-lines span {
  height: 6px;
  border-radius: 3px;
  background: rgba(124, 58, 237, 0.25);
}
.ds-lines span:nth-child(even) { width: 70%; }
.phase-3 .ds-lines { opacity: 0.25; }
.ds-count {
  position: absolute;
  inset: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 0.1rem;
  opacity: 0;
  transform: scale(0.8);
  transition: opacity 0.4s ease 0.6s, transform 0.4s ease 0.6s;
}
.ds-num {
  font-size: 1.9rem;
  font-weight: 800;
  color: #7c3aed;
  line-height: 1;
  letter-spacing: -0.01em;
}
.ds-unit {
  font-size: 0.8rem;
  font-weight: 600;
  color: #7c3aed;
  opacity: 0.65;
}
.phase-3 .ds-count {
  opacity: 1;
  transform: scale(1);
}
.ds-label {
  margin-top: 0.5rem;
  font-weight: 800;
  color: #7c3aed;
  font-size: 1.05rem;
}
.ds-sub {
  font-size: 0.8rem;
  opacity: 0.55;
}

.phase-3 .ds-box {
  box-shadow: 0 0 0 4px rgba(124, 58, 237, 0.15), 0 16px 34px rgba(124, 58, 237, 0.25);
  border-color: #7c3aed;
}
.phase-3 .ds-fill {
  height: 100%;
  transition: height 1.3s ease 0.35s;
}

.mail-layer {
  position: absolute;
  inset: 0;
  pointer-events: none;
  z-index: 5;
}
.mail {
  position: absolute;
  width: 40px;
  height: 32px;
  border-radius: 8px;
  background: #fff;
  box-shadow: 0 6px 16px rgba(0, 0, 0, 0.16);
  display: grid;
  place-items: center;
  opacity: 0;
  transform: translate(0, 0) scale(0.5);
}
.mail-ico {
  font-size: 18px;
  line-height: 1;
}
.mail-check {
  position: absolute;
  top: -8px;
  right: -8px;
  width: 18px;
  height: 18px;
  border-radius: 50%;
  background: #16a34a;
  color: #fff;
  font-size: 12px;
  font-weight: 800;
  display: grid;
  place-items: center;
  opacity: 0;
  transform: scale(0);
  transition: opacity 0.3s ease, transform 0.3s ease;
}

.phase-1 .mail,
.phase-2 .mail,
.phase-3 .mail { opacity: 1; }

.phase-1 .mail {
  animation: toHub 1s cubic-bezier(0.35, 0, 0.2, 1) both;
  animation-delay: calc(var(--i) * 0.14s);
}

.phase-2 .mail {
  transform: translate(var(--hx), var(--hy)) scale(1);
  transition: transform 0.35s ease;
}
.phase-2 .mail-check,
.phase-3 .mail-check {
  opacity: 1;
  transform: scale(1);
  transition-delay: calc(var(--i) * 0.12s + 0.15s);
}

.phase-3 .mail {
  animation: toDataset 0.95s cubic-bezier(0.4, 0, 0.25, 1) both;
  animation-delay: calc(var(--i) * 0.1s);
}

@keyframes toHub {
  0% { transform: translate(0, 0) scale(0.5); opacity: 0; }
  18% { transform: translate(0, -50px) scale(0.9); opacity: 1; }
  100% { transform: translate(var(--hx), var(--hy)) scale(1); opacity: 1; }
}
@keyframes toDataset {
  0% { transform: translate(var(--hx), var(--hy)) scale(1); opacity: 1; }
  72% { transform: translate(var(--dx), var(--dy)) scale(0.8); opacity: 1; }
  100% { transform: translate(var(--dx), var(--dy)) scale(0.3); opacity: 0; }
}
@keyframes scan {
  0%, 100% { transform: translate(0, 0) rotate(-8deg); }
  50% { transform: translate(7px, 9px) rotate(7deg); }
}
@keyframes pulse {
  0%, 100% { transform: scale(1); box-shadow: 0 10px 24px rgba(0, 0, 0, 0.18); }
  50% { transform: scale(1.06); box-shadow: 0 14px 30px rgba(0, 0, 0, 0.26); }
}

.caption {
  padding: 0.7rem 1.6rem;
  border-radius: 999px;
  background: rgba(124, 58, 237, 0.08);
  border: 1px solid rgba(124, 58, 237, 0.28);
  color: #7c3aed;
  font-weight: 700;
  font-size: 1.15rem;
  transition: all 0.3s ease;
}
.caption.cap-3 {
  background: rgba(22, 163, 74, 0.1);
  border-color: rgba(22, 163, 74, 0.35);
  color: #16a34a;
}
</style>
