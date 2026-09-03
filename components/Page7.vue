<script setup>
import { computed } from 'vue'
import { useSlideContext } from '@slidev/client'

const { $clicks: clicks } = useSlideContext()
const stage = computed(() => clicks.value ?? 0)
</script>

<template>
  <span v-click="1" class="anchor" />

  <div class="tech-box">
    <div class="tech-title">BertForSequenceClassification</div>
    <div class="tech-row"><span>Learning Rate</span><span>2×10⁻⁵</span></div>
    <div class="tech-row"><span>Batch Size</span><span>8</span></div>
    <div class="tech-row"><span>Epochs</span><span>5</span></div>
    <div class="tech-row"><span>Optimizer</span><span>AdamW</span></div>
  </div>

  <div class="stage">
    <div class="bert-logo">
      <svg class="bert-rings" viewBox="0 0 200 200" aria-hidden="true">
        <defs>
          <marker
            id="p7ah"
            markerUnits="userSpaceOnUse"
            markerWidth="26"
            markerHeight="26"
            viewBox="0 0 14 14"
            refX="6"
            refY="7"
            orient="auto"
          >
            <path d="M0,0 L14,7 L0,14 Z" fill="#c6cad0" />
          </marker>
        </defs>
        <path
          d="M26.71 73.32 A 78 78 0 0 1 173.29 73.32"
          fill="none"
          stroke="#c6cad0"
          stroke-width="13"
          stroke-linecap="round"
          marker-end="url(#p7ah)"
        />
        <path
          d="M173.29 126.68 A 78 78 0 0 1 26.71 126.68"
          fill="none"
          stroke="#c6cad0"
          stroke-width="13"
          stroke-linecap="round"
          marker-end="url(#p7ah)"
        />
      </svg>
      <div class="bert-word">
        <span class="bw-inner"><span style="color: #4285f4">B</span><span style="color: #ea4335">E</span><span style="color: #fbbc05">R</span><span style="color: #34a853">T</span></span>
      </div>
    </div>

    <div class="hero-line" />

    <div class="idcards" v-if="stage >= 1">
      <div class="idcard">
        <span class="idcard-ic">🇹🇷</span>
        <span>Türkçe için <b>önceden eğitilmiş</b> BERT modeli</span>
      </div>
      <div class="idcard">
        <span class="idcard-ic">🎯</span>
        <span>Etik / etik dışı sınıflandırma için <b>fine-tune</b> edildi</span>
      </div>
    </div>

    <div class="flip" v-if="stage >= 1">
      <div class="flip-mail">
        <span class="scan" />
        <span class="mk m1">Benzer işlerin daha kısa sürede sonuçlandırılabildiğini düşünürsek</span>,
        bu konuda <span class="mk m2">neden bu kadar zorlanıldığını anlamak biraz güç</span>.
      </div>

      <div class="flip-mid">
        <div class="checks">
          <span class="chk c1">küfür? ✗</span>
          <span class="chk c2">hakaret? ✗</span>
          <span class="chk c3">tehdit? ✗</span>
        </div>

        <div class="tone">
          <span class="tone-label">ton ölçer</span>
          <span class="tone-bar"><span class="tone-fill" /></span>
          <span class="tone-val">%88 · pasif-agresif</span>
        </div>
      </div>

      <div class="stamps">
        <span class="stamp clean">TEMİZ</span>
        <span class="stamp toxic">ETİK DIŞI</span>
      </div>
    </div>
  </div>
</template>

<style scoped>
.anchor { position: absolute; width: 0; height: 0; overflow: hidden; }

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
  margin-top: 1.5rem;
}

.bert-logo {
  position: relative;
  width: 150px;
  height: 150px;
  animation: box-in 0.5s ease both;
}
.bert-rings {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  animation: spin 16s linear infinite;
}
.bert-word {
  position: absolute;
  inset: 0;
  display: flex;
  align-items: center;
  justify-content: center;
}
.bw-inner {
  white-space: nowrap;
  font-size: 1.7rem;
  font-weight: 800;
  letter-spacing: 0.02em;
}

.hero-line {
  width: 1px;
  height: 20px;
  background: rgba(124, 58, 237, 0.4);
}

/* --- click 1: kimlik kartları --- */
.idcards {
  display: flex;
  gap: 1.2rem;
  margin-top: 0.2rem;
}
.idcard {
  display: flex;
  align-items: center;
  gap: 0.6rem;
  width: 260px;
  padding: 0.6rem 0.9rem;
  border-radius: 12px;
  background: rgba(124, 58, 237, 0.06);
  border: 1px solid rgba(124, 58, 237, 0.22);
  font-size: 0.85rem;
  line-height: 1.3;
  text-align: left;
  animation: box-in 0.75s cubic-bezier(0.22, 1, 0.36, 1) both;
}
.idcard:nth-child(1) { animation-delay: 0.08s; }
.idcard:nth-child(2) { animation-delay: 0.24s; }
.idcard-ic {
  flex-shrink: 0;
  width: 30px;
  height: 30px;
  display: grid;
  place-items: center;
  font-size: 1.05rem;
  border-radius: 8px;
  background: #fff;
  border: 1px solid rgba(124, 58, 237, 0.25);
}
.idcard b { color: #7c3aed; }

.flip {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1rem;
  margin-top: 1.4rem;
}

.flip-mail {
  position: relative;
  overflow: hidden;
  max-width: 560px;
  padding: 1rem 1.4rem;
  border-radius: 12px;
  background: rgba(124, 58, 237, 0.05);
  border: 1px solid rgba(124, 58, 237, 0.2);
  font-size: 1.05rem;
  line-height: 1.7;
  text-align: center;
  animation: rise 0.8s cubic-bezier(0.22, 1, 0.36, 1) 0.4s both;
}

.scan {
  position: absolute;
  top: 0;
  bottom: 0;
  left: -35%;
  width: 35%;
  background: linear-gradient(
    90deg,
    transparent,
    rgba(124, 58, 237, 0.3),
    transparent
  );
  animation: sweep 1.6s ease-in-out 1.2s 1 both;
}

.mk {
  border-radius: 3px;
  padding: 0 2px;
  -webkit-box-decoration-break: clone;
  box-decoration-break: clone;
}
.m1 { animation: tint 0.45s ease forwards 3.9s; }
.m2 { animation: tint 0.45s ease forwards 4.5s; }

.flip-mid {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.5rem;
  min-height: 2.6rem;
}

.checks {
  display: flex;
  gap: 0.5rem;
}
.chk {
  font-size: 0.75rem;
  font-weight: 600;
  color: #666;
  background: rgba(120, 120, 120, 0.1);
  border: 1px solid rgba(120, 120, 120, 0.22);
  border-radius: 999px;
  padding: 0.15rem 0.6rem;
  opacity: 0;
  animation: pop-in 0.35s ease forwards;
}
.c1 { animation-delay: 1.4s; }
.c2 { animation-delay: 1.9s; }
.c3 { animation-delay: 2.4s; }

.tone {
  display: flex;
  align-items: center;
  gap: 0.55rem;
  font-size: 0.78rem;
  opacity: 0;
  animation: rise 0.5s ease forwards 5s;
}
.tone-label { color: #7c3aed; font-weight: 700; letter-spacing: 0.03em; }
.tone-bar {
  width: 150px;
  height: 8px;
  border-radius: 999px;
  background: rgba(124, 58, 237, 0.15);
  overflow: hidden;
}
.tone-fill {
  display: block;
  height: 100%;
  width: 0;
  border-radius: 999px;
  background: linear-gradient(90deg, #a855f7, #d64545);
  animation: fill 1.2s cubic-bezier(0.22, 1, 0.36, 1) forwards 5.3s;
}
.tone-val { color: #b23b3b; font-weight: 700; }

.stamps {
  position: relative;
  width: 230px;
  height: 54px;
}
.stamp {
  position: absolute;
  inset: 0;
  display: grid;
  place-items: center;
  font-weight: 900;
  letter-spacing: 0.08em;
  border-radius: 10px;
}
.stamp.clean {
  color: #7a7a7a;
  border: 3px solid rgba(120, 120, 120, 0.5);
  font-size: 1.15rem;
  transform: rotate(-6deg) scale(0.6);
  opacity: 0;
  animation:
    drop 0.5s cubic-bezier(0.34, 1.56, 0.64, 1) forwards 2.9s,
    dim 0.4s ease forwards 5.9s;
}
.stamp.toxic {
  color: #fff;
  background: #d64545;
  font-size: 1.25rem;
  transform: rotate(4deg) scale(2.6);
  opacity: 0;
  animation: slam 0.55s cubic-bezier(0.3, 1.4, 0.5, 1) forwards 5.95s;
}

@keyframes sweep {
  from { left: -35%; }
  to   { left: 100%; }
}
@keyframes tint {
  to {
    background: rgba(214, 69, 69, 0.13);
    color: #b23b3b;
    box-shadow: inset 0 -2px 0 #d64545;
  }
}
@keyframes fill { to { width: 88%; } }
@keyframes spin { to { transform: rotate(360deg); } }
@keyframes rise {
  from { opacity: 0; transform: translateY(20px); }
  to   { opacity: 1; transform: translateY(0); }
}
@keyframes pop-in {
  from { opacity: 0; transform: scale(0.8); }
  to   { opacity: 1; transform: scale(1); }
}
@keyframes drop {
  to { opacity: 1; transform: rotate(-6deg) scale(1); }
}
@keyframes dim {
  to { opacity: 0.3; filter: grayscale(1); }
}
@keyframes slam {
  0%   { opacity: 0; transform: rotate(4deg) scale(2.6); }
  70%  { opacity: 1; transform: rotate(4deg) scale(0.9); }
  100% { opacity: 1; transform: rotate(4deg) scale(1); }
}
@keyframes box-in {
  from { opacity: 0; transform: translateY(18px) scale(0.94); }
  to   { opacity: 1; transform: translateY(0) scale(1); }
}
</style>
