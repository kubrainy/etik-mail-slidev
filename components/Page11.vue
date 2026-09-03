<script setup>
import { computed } from 'vue'
import { useSlideContext } from '@slidev/client'

const { $clicks: clicks } = useSlideContext()

const stage = computed(() => {
  const c = clicks.value ?? 0
  if (c <= 0) return 'inbox'
  if (c === 1) return 'composeArm'
  if (c === 2) return 'composeEmpty'
  if (c === 3) return 'composeSubject'
  if (c === 4) return 'composeFilled'
  return 'result'
})

const composeOpen = computed(() =>
  ['composeEmpty', 'composeSubject', 'composeFilled'].includes(stage.value),
)
const subjectTyped = computed(() =>
  ['composeSubject', 'composeFilled'].includes(stage.value),
)
const filled = computed(() => stage.value === 'composeFilled')
const armed = computed(() => stage.value === 'composeArm')
const dimmed = computed(() => composeOpen.value || stage.value === 'result')

const emails = [
  { name: 'Ali Demir', subject: 'Proje sunumu', preview: 'Yarınki sunum için son kontrolleri yapalım mı?', date: '16 Haz', star: false, active: true },
  { name: 'Ayşe Kaya', subject: 'Haftalık rapor', preview: 'Rapor ektedir, inceleyip geri bildirim verir misiniz?', date: '15 Haz', star: true, attach: true },
  { name: 'Mehmet Yıldız', subject: 'Toplantı notları', preview: 'Dünkü toplantı notlarını paylaşıyorum.', date: '14 Haz', star: false },
  { name: 'Zeynep Arslan', subject: 'Tasarım onayı', preview: 'Yeni arayüz tasarımı için onayınızı bekliyorum.', date: '13 Haz', star: false },
  { name: 'Can Öztürk', subject: 'Sunucu bakımı', preview: 'Cumartesi gece bakım planı hakkında bilgilendirme.', date: '12 Haz', star: true },
]

const steps = [
  { title: 'Mail içeriği hazırlanıyor', desc: 'Konu ve gövde alanları kontrol ediliyor.' },
  { title: 'Metin birleştiriliyor', desc: 'Konu ve gövde tek metin haline getiriliyor.' },
  { title: 'Metin temizleniyor', desc: 'HTML etiketleri ve fazla boşluklar temizleniyor.' },
  { title: 'BERT tokenizer hazırlanıyor', desc: "Metin token'lara ayrılıyor." },
  { title: 'Yerel model servisine gönderiliyor', desc: 'FastAPI üzerinden BERT modeline istek atılıyor.' },
  { title: 'Model kararı yorumlanıyor', desc: 'Softmax skoru karara dönüştürülüyor.' },
]
</script>

<template>
  <div class="sim-wrap">
    <span v-click="1" class="click-anchor" />
    <span v-click="2" class="click-anchor" />
    <span v-click="3" class="click-anchor" />
    <span v-click="4" class="click-anchor" />
    <span v-click="5" class="click-anchor" />

    <div class="app">
      <aside class="side">
        <div class="brand">
          <span class="brand-mark">✉</span>
          <span class="brand-name">Etik Mail</span>
          <span class="brand-collapse">‹</span>
        </div>

        <div
          class="compose-btn"
          :class="{ hint: stage === 'inbox', pressed: armed }"
        >
          <span class="pencil">✎</span> Mail Yaz
        </div>

        <nav class="nav">
          <div class="nav-item active"><span class="nav-ic">▤</span> Gelen Kutusu</div>
          <div class="nav-item"><span class="nav-ic">➤</span> Gönderilen</div>
          <div class="nav-item"><span class="nav-ic">🗑</span> Çöp Kutusu</div>
        </nav>
      </aside>

      <section class="main">
        <header class="topbar">
          <span class="menu">☰</span>
          <span class="page-title">Gelen Kutusu</span>
          <span class="spacer" />
          <span class="moon">☾</span>
          <span class="user">
            <span class="user-av">KÇ</span>
            <span class="user-name">Kübra Çetinkaya</span>
          </span>
          <span class="logout">Çıkış</span>
        </header>

        <div class="toolbar">
          <span class="chk" />
          <span class="refresh">⟳</span>
          <div class="search">
            <span class="s-ic">⚲</span>
            <span class="s-ph">E-postalarda arama yapın</span>
          </div>
        </div>

        <div class="list">
          <div
            v-for="(m, i) in emails"
            :key="i"
            class="row"
            :class="{ 'row-active': m.active }"
          >
            <span class="chk" />
            <span class="star" :class="{ on: m.star }">{{ m.star ? '★' : '☆' }}</span>
            <span class="avatar">{{ m.name[0] }}</span>
            <div class="row-text">
              <div class="row-top">
                <span class="row-name">{{ m.name }}</span>
              </div>
              <div class="row-subject">{{ m.subject }}</div>
              <div class="row-preview">{{ m.preview }}</div>
            </div>
            <div class="row-meta">
              <span class="row-date">{{ m.date }}</span>
              <span v-if="m.attach" class="row-clip">📎</span>
            </div>
          </div>
        </div>
      </section>

      <Transition name="fade">
        <div v-if="dimmed" class="scrim" />
      </Transition>

      <Transition name="pop">
        <div v-if="composeOpen" class="modal compose">
          <div class="modal-head">
            <span class="modal-title">Yeni İleti</span>
            <span class="modal-x">✕</span>
          </div>
          <div class="field">
            <span class="f-label">Kime</span>
            <span class="f-value">kubra@example.com</span>
            <span class="f-cc">Cc / Bcc</span>
          </div>
          <div class="field">
            <span class="f-label">Konu</span>
            <span v-if="subjectTyped" class="f-value">Dosya Teslimi</span>
            <span v-else class="f-value ph">Konu</span>
          </div>
          <div class="compose-body">
            <template v-if="filled">
              <p>Merhaba,</p>
              <p>
                Dosyayı yeniden gönderdim. Umarım bu kez gözden kaçmaz ve
                süreci tekrar hatırlatmak zorunda kalmam.
              </p>
              <p>İyi çalışmalar.</p>
            </template>
          </div>
          <div class="compose-foot">
            <div class="rte">
              <b>B</b><i>I</i><u>U</u><s>S</s>
              <span class="rte-sep" />
              <span>•</span><span>1.</span><span>📎</span>
            </div>
            <span class="send-btn">Gönder</span>
          </div>
        </div>
      </Transition>

      <Transition name="fade">
        <div v-if="stage === 'result'" class="modal result">
          <div class="res-topline">
            <span class="res-kicker">LOCAL FASTAPI + BERT</span>
            <span class="res-top-right">
              <span class="pill-toxic reveal-late">TOXIC</span>
              <span class="res-time reveal-late">⏱ 13.2 sn</span>
            </span>
          </div>
          <h2 class="res-title">Etik Model Kontrolü</h2>
          <div class="res-sub reveal-late">Gönderim durduruldu</div>

          <div class="res-grid">
            <div class="analysis">
              <div class="analysis-head">Analiz süreci</div>
              <div
                v-for="(s, i) in steps"
                :key="i"
                class="step"
                :style="{ '--i': i }"
              >
                <span class="step-ic">
                  <span class="step-spin" />
                  <span class="step-check">✓</span>
                </span>
                <div class="step-text">
                  <div class="step-title">{{ s.title }}</div>
                  <div class="step-desc">{{ s.desc }}</div>
                </div>
                <span class="step-done">Tamamlandı</span>
              </div>
            </div>

            <div class="res-right">
              <div class="res-pending">
                <span class="pend-spin" />
                <span>Model analiz ediyor…</span>
              </div>
              <div class="decision reveal-after">
                <div class="decision-title">Model kararı: Gönderilemez</div>
                <div class="decision-main">%100 toxic — Gönderilemez</div>
                <div class="decision-desc">
                  Metin saldırgan, iğneleyici, tehditkâr veya etik açıdan uygunsuz olabilir.
                </div>
                <div class="decision-foot">ETİKET: TOXIC &nbsp;·&nbsp; ⏱ 13.2 sn</div>
              </div>

              <div class="summary reveal-after">
                <div class="summary-title">Model özeti</div>
                <ul>
                  <li><b>MODEL:</b> dbmdz/bert-base-turkish-cased fine-tune</li>
                  <li><b>ENDPOINT:</b> 127.0.0.1:8000/predict</li>
                  <li><b>KARAR:</b> TOXIC</li>
                  <li><b>TOKSİK SKOR:</b> %100</li>
                  <li><b>ETİK SKOR:</b> %0</li>
                </ul>
              </div>
            </div>
          </div>

          <div class="res-foot reveal-after">
            <div class="chips">
              <span class="chip">Konu: 13 karakter</span>
              <span class="chip">Gövde: 16 kelime</span>
              <span class="chip">Token: 36 / 256</span>
              <span class="chip">127.0.0.1:8000/predict</span>
            </div>
            <div class="res-actions">
              <span class="btn-ghost">Düzenle</span>
              <span class="btn-primary">Tamam</span>
            </div>
          </div>
        </div>
      </Transition>
    </div>
  </div>
</template>

<style scoped>
.sim-wrap {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
}
.click-anchor {
  position: absolute;
  width: 0;
  height: 0;
  overflow: hidden;
  pointer-events: none;
}

.app {
  position: relative;
  width: 952px;
  height: 542px;
  display: flex;
  background: #f7f8fa;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 24px 60px rgba(0, 0, 0, 0.28);
  color: #1f2937;
  font-size: 12px;
  text-align: left;
}

.side {
  width: 208px;
  flex-shrink: 0;
  background: #ffffff;
  border-right: 1px solid #eceef1;
  padding: 14px 12px;
}
.brand {
  display: flex;
  align-items: center;
  gap: 8px;
  font-weight: 800;
  font-size: 14px;
  padding: 4px 6px 14px;
}
.brand-mark {
  width: 22px; height: 22px;
  display: grid; place-items: center;
  background: #2563eb; color: #fff;
  border-radius: 6px; font-size: 12px;
}
.brand-collapse { margin-left: auto; opacity: 0.4; font-size: 15px; }
.compose-btn {
  display: flex; align-items: center; gap: 8px;
  border: 1px solid #dfe3e8;
  border-radius: 12px;
  padding: 10px 14px;
  font-weight: 700;
  color: #1d4ed8;
  background: #fff;
  box-shadow: 0 1px 2px rgba(0,0,0,0.04);
}
.compose-btn.hint {
  border-color: #2563eb;
  box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.18);
}
.compose-btn.pressed {
  background: #2563eb;
  color: #fff;
  border-color: #2563eb;
  transform: scale(0.96);
  box-shadow: 0 0 0 4px rgba(37, 99, 235, 0.22);
}
.compose-btn.pressed .pencil { color: #fff; }
.compose-btn { transition: transform 0.15s ease, background 0.15s ease, box-shadow 0.15s ease; }
.pencil { color: #2563eb; }
.nav { margin-top: 16px; display: flex; flex-direction: column; gap: 4px; }
.nav-item {
  display: flex; align-items: center; gap: 10px;
  padding: 9px 12px; border-radius: 8px;
  color: #4b5563; font-weight: 600;
}
.nav-item.active { background: #e8f0fe; color: #1a56db; }
.nav-ic { width: 16px; text-align: center; opacity: 0.85; }

.main { flex: 1; display: flex; flex-direction: column; min-width: 0; }
.topbar {
  height: 50px;
  display: flex; align-items: center; gap: 14px;
  padding: 0 18px;
  border-bottom: 1px solid #eceef1;
  background: #fff;
}
.menu { font-size: 15px; opacity: 0.6; }
.page-title { font-size: 15px; font-weight: 700; }
.spacer { flex: 1; }
.moon { opacity: 0.55; font-size: 14px; }
.user { display: flex; align-items: center; gap: 8px; }
.user-av {
  width: 24px; height: 24px; border-radius: 50%;
  background: #2563eb; color: #fff;
  display: grid; place-items: center;
  font-size: 10px; font-weight: 700;
}
.user-name { font-weight: 600; font-size: 12px; }
.logout {
  border: 1px solid #e0e3e8; border-radius: 999px;
  padding: 4px 12px; font-size: 11px; color: #6b7280;
}

.toolbar {
  display: flex; align-items: center; gap: 12px;
  padding: 12px 18px;
  background: #fff;
  border-bottom: 1px solid #f0f1f3;
}
.chk {
  width: 14px; height: 14px; border-radius: 3px;
  border: 1.5px solid #c4c9d0; flex-shrink: 0;
}
.refresh { opacity: 0.5; font-size: 14px; }
.search {
  flex: 1; display: flex; align-items: center; gap: 8px;
  border: 1px solid #e3e6ea; border-radius: 999px;
  padding: 7px 14px; color: #9aa1ab;
}
.s-ic { transform: rotate(45deg); display: inline-block; }

.list { flex: 1; overflow: hidden; background: #fff; }
.row {
  display: flex; align-items: flex-start; gap: 10px;
  padding: 11px 18px;
  border-bottom: 1px solid #f1f2f4;
}
.row-active { background: #eef4ff; box-shadow: inset 3px 0 0 #2563eb; }
.star { color: #cfd4da; font-size: 13px; margin-top: 1px; }
.star.on { color: #f5b301; }
.avatar {
  width: 26px; height: 26px; border-radius: 50%;
  background: #dce9ff; color: #2563eb;
  display: grid; place-items: center;
  font-size: 11px; font-weight: 700; flex-shrink: 0;
}
.row-text { flex: 1; min-width: 0; }
.row-name { font-weight: 700; font-size: 12.5px; }
.row-subject { font-size: 12px; margin-top: 1px; }
.row-preview { font-size: 11px; color: #8b929c; margin-top: 2px; }
.row-meta { text-align: right; color: #9aa1ab; font-size: 11px; display: flex; flex-direction: column; align-items: flex-end; gap: 6px; }
.row-clip { font-size: 11px; }

.scrim {
  position: absolute; inset: 0;
  background: rgba(30, 34, 45, 0.32);
  backdrop-filter: blur(1px);
}
.modal {
  position: absolute;
  left: 50%; top: 50%;
  transform: translate(-50%, -50%);
  background: #fff;
  border-radius: 12px;
  box-shadow: 0 30px 70px rgba(0, 0, 0, 0.35);
  overflow: hidden;
}
.compose { width: 620px; }
.modal-head {
  display: flex; align-items: center;
  background: #eaf1ff; padding: 10px 16px;
  font-weight: 700; color: #1d4ed8;
}
.modal-title { flex: 1; }
.modal-x { opacity: 0.5; }
.field {
  display: flex; align-items: center; gap: 12px;
  padding: 9px 16px; border-bottom: 1px solid #eef0f2;
  font-size: 12px;
}
.f-label { color: #8b929c; width: 40px; }
.f-value { flex: 1; }
.f-value.ph { color: #b7bcc4; }
.f-cc { color: #8b929c; font-size: 11px; }
.compose-body {
  min-height: 190px;
  padding: 14px 16px;
  font-size: 12.5px;
  line-height: 1.7;
}
.compose-body p { margin: 0 0 12px; }
.compose-foot {
  display: flex; align-items: center;
  padding: 10px 16px;
  border-top: 1px solid #eef0f2;
}
.rte {
  flex: 1; display: flex; align-items: center; gap: 12px;
  color: #6b7280; font-size: 12px;
}
.rte s { opacity: 0.8; }
.rte-sep { width: 1px; height: 14px; background: #dfe3e8; }
.send-btn {
  background: #2563eb; color: #fff;
  padding: 7px 20px; border-radius: 8px;
  font-weight: 700; font-size: 12px;
}

.result {
  width: 892px;
  max-height: calc(100% - 16px);
  display: flex;
  flex-direction: column;
  padding: 12px 18px 12px;
}
.res-topline { display: flex; align-items: center; flex-shrink: 0; }
.res-kicker {
  flex: 1;
  font-size: 9.5px; letter-spacing: 0.14em;
  color: #9aa1ab; font-weight: 700;
}
.res-top-right { display: flex; align-items: center; gap: 10px; }
.pill-toxic {
  background: #fdecec; color: #d64545;
  border: 1px solid #f3c9c9;
  padding: 2px 10px; border-radius: 999px;
  font-size: 10px; font-weight: 800; letter-spacing: 0.05em;
}
.res-time { font-size: 11px; color: #8b929c; }
.res-title { margin: 4px 0 2px; font-size: 18px; font-weight: 800; flex-shrink: 0; }
.res-sub { color: #6b7280; font-size: 12px; margin-bottom: 10px; flex-shrink: 0; }

.res-grid {
  display: grid;
  grid-template-columns: 1fr 330px;
  grid-template-rows: 1fr;
  gap: 14px;
  flex: 1;
  min-height: 0;
}
.analysis {
  border: 1px solid #edeef1; border-radius: 10px;
  padding: 10px; background: #fbfbfc;
  min-height: 0;
}
.res-right { min-height: 0; }
.analysis-head { font-weight: 700; font-size: 12px; margin-bottom: 7px; }
.step {
  --d: 0.55s;
  display: flex; align-items: center; gap: 10px;
  background: #fff;
  border: 1px solid #e7e9ec;
  border-left: 3px solid #cbd5e1;
  border-radius: 8px;
  padding: 6px 10px;
  margin-bottom: 5px;
  opacity: 0;
  animation: stepReveal 0.9s ease forwards;
  animation-delay: calc(var(--i) * var(--d));
}
.step:last-child { margin-bottom: 0; }
@keyframes stepReveal {
  0%   { opacity: 0; transform: translateY(10px); border-left-color: #cbd5e1; background: #fbfcfe; }
  35%  { opacity: 1; transform: translateY(0);    border-left-color: #2563eb; background: #f1f6ff; }
  100% { opacity: 1; transform: translateY(0);    border-left-color: #34a853; background: #fff; }
}
.step-ic {
  position: relative;
  width: 16px; height: 16px;
  flex-shrink: 0;
}
.step-spin {
  position: absolute; inset: 0;
  border-radius: 50%;
  border: 2px solid #e2e8f0;
  border-top-color: #2563eb;
  animation:
    spin 0.7s linear infinite,
    fadeOut 0.2s ease forwards calc(var(--i) * var(--d) + 0.75s);
}
.step-check {
  position: absolute; inset: 0;
  border-radius: 50%;
  background: #e6f4ea; color: #1e8e3e;
  display: grid; place-items: center;
  font-size: 10px; font-weight: 800;
  transform: scale(0);
  animation: pop 0.3s ease forwards calc(var(--i) * var(--d) + 0.75s);
}
.step-text { flex: 1; min-width: 0; }
.step-title { font-weight: 700; font-size: 11.5px; }
.step-desc { font-size: 10.5px; color: #8b929c; margin-top: 1px; }
.step-done {
  font-size: 10px; color: #1e8e3e; font-weight: 600; flex-shrink: 0;
  opacity: 0;
  animation: fadeIn 0.3s ease forwards calc(var(--i) * var(--d) + 0.8s);
}
@keyframes spin { to { transform: rotate(360deg); } }
@keyframes fadeOut { to { opacity: 0; } }

.res-right { display: flex; flex-direction: column; gap: 12px; position: relative; }
.res-pending {
  position: absolute; inset: 0;
  display: flex; flex-direction: column;
  align-items: center; justify-content: center;
  gap: 12px;
  color: #8b929c; font-size: 12px; font-weight: 600;
  animation: fadeOut 0.4s ease forwards 3.8s;
}
.pend-spin {
  width: 28px; height: 28px; border-radius: 50%;
  border: 3px solid #e2e8f0; border-top-color: #2563eb;
  animation: spin 0.8s linear infinite;
}
.decision {
  background: #fdecec;
  border: 1px solid #f3c9c9;
  border-radius: 10px;
  padding: 12px 14px;
}
.decision-title { font-weight: 800; font-size: 12.5px; color: #b23b3b; }
.decision-main { font-weight: 800; font-size: 12px; margin-top: 6px; color: #c0392b; }
.decision-desc { font-size: 10.5px; color: #7a5a5a; margin-top: 4px; line-height: 1.5; }
.decision-foot { font-size: 10px; color: #9a6b6b; margin-top: 8px; font-weight: 700; letter-spacing: 0.03em; }
.summary {
  background: #f7f8fa;
  border: 1px solid #edeef1;
  border-radius: 10px;
  padding: 12px 14px;
}
.summary-title { font-weight: 700; font-size: 12px; margin-bottom: 6px; }
.summary ul { margin: 0; padding-left: 16px; }
.summary li { font-size: 10.5px; line-height: 1.7; color: #4b5563; }

.res-foot {
  display: flex; align-items: center;
  margin-top: 10px; gap: 12px;
  flex-shrink: 0;
}
.chips { flex: 1; display: flex; flex-wrap: wrap; gap: 6px; }
.chip {
  border: 1px solid #e6e8ec; border-radius: 999px;
  padding: 3px 10px; font-size: 9.5px; color: #6b7280;
}
.res-actions { display: flex; gap: 8px; }
.btn-ghost {
  border: 1px solid #d7dbe0; border-radius: 8px;
  padding: 6px 16px; font-size: 11px; font-weight: 600; color: #4b5563;
}
.btn-primary {
  background: #2563eb; color: #fff;
  border-radius: 8px; padding: 6px 20px;
  font-size: 11px; font-weight: 700;
}

.reveal-after {
  opacity: 0;
  transform: translateY(6px);
  animation: stepIn 0.5s ease forwards;
  animation-delay: 3.95s;
}
.reveal-late {
  opacity: 0;
  animation: fadeIn 0.5s ease forwards;
  animation-delay: 3.7s;
}

@keyframes stepIn {
  to { opacity: 1; transform: translateY(0); }
}
@keyframes fadeIn {
  to { opacity: 1; }
}
@keyframes pop {
  to { transform: scale(1); }
}

.fade-enter-active, .fade-leave-active { transition: opacity 0.25s ease; }
.fade-enter-from, .fade-leave-to { opacity: 0; }

.pop-enter-active { transition: opacity 0.28s ease, transform 0.28s cubic-bezier(0.2, 0.9, 0.3, 1.2); }
.pop-leave-active { transition: opacity 0.18s ease, transform 0.18s ease; }
.pop-enter-from { opacity: 0; transform: translate(-50%, -46%) scale(0.94); }
.pop-leave-to { opacity: 0; transform: translate(-50%, -50%) scale(0.97); }
</style>
