<script setup>
import { useSlideContext } from '@slidev/client'
const { $clicks: clicks } = useSlideContext()
</script>

<template>
<div class="grid grid-cols-2 gap-8 items-center text-left">

<div class="intro">
  <div class="eyebrow">IDAP'26 · 2026</div>

  <h1 class="intro-title">
    Detecting Unethical Language in Turkish Corporate Emails
  </h1>

  <p class="intro-subtitle">
    Türkçe Kurumsal E-Postalarda<br>Etik Dışı Dil Tespiti
  </p>

  <div class="intro-meta">
    <div class="intro-authors">
      <strong>Kübra Çetinkaya</strong> · Sezi Güngörmüş · Şerif Ali Sadık
    </div>
    <div class="intro-affil">Kütahya Dumlupınar Üniversitesi</div>
  </div>
</div>

<div class="email-card">
  <div class="email-header">
    <div class="email-dot"></div>
    <div class="email-dot"></div>
    <div class="email-dot"></div>
    <span class="ml-2 opacity-50 text-xs">Gelen Kutusu</span>
  </div>
  <div class="email-body">
    <p class="mb-2 opacity-60 text-xs">Konu: Proje Teslim Tarihi</p>
    <p>
      Merhaba,<br><br>
      <span class="flag" :class="{ 'flag--on': clicks >= 1 }">Sanırım herkes gibi sen de</span>
      son teslim tarihini kaçırdın.
      <span class="flag" :class="{ 'flag--on': clicks >= 2 }">Tabii senden</span>
      zaten fazlasını beklemiyordum.<br><br>
      <span class="flag" :class="{ 'flag--on': clicks >= 3 }">Bu iş sende olmasa</span>
      belki ekip daha hızlı ilerlerdi.<br><br>
      İyi çalışmalar.
    </p>
  </div>

  <div v-click="1" class="tag tag-1">⚠ Küçümseyici</div>
  <div v-click="2" class="tag tag-2">⚠ Pasif-agresif</div>
  <div v-click="3" class="tag tag-3">⚠ Baskılayıcı</div>
</div>

</div>
</template>
<style scoped>
.intro {
  display: flex;
  flex-direction: column;
  gap: 0.85rem;
}
.eyebrow {
  font-size: 0.72rem;
  font-weight: 700;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: #7c3aed;
}
.intro-title {
  margin: 0;
  font-size: 2.1rem;
  font-weight: 800;
  line-height: 1.2;
  letter-spacing: -0.02em;
  background: linear-gradient(120deg, #7c3aed 0%, #db2777 100%);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
}
.intro-subtitle {
  margin: 0;
  font-size: 1.02rem;
  line-height: 1.5;
  opacity: 0.7;
}
.intro-meta {
  margin-top: 0.7rem;
  padding-top: 0.9rem;
  border-top: 1px solid rgba(124, 58, 237, 0.2);
}
.intro-authors {
  font-size: 0.9rem;
}
.intro-authors strong {
  color: #7c3aed;
}
.intro-affil {
  font-size: 0.8rem;
  opacity: 0.55;
  margin-top: 0.15rem;
}
.email-card {
  position: relative;
  max-width: 420px;
  margin-left: auto;
  margin-right: 4.5rem;
  background: white;
  border-radius: 12px;
  box-shadow: 0 20px 40px rgba(0,0,0,0.15);
  font-size: 0.8rem;
  color: #333;
}
.email-header {
  display: flex;
  align-items: center;
  gap: 6px;
  padding: 8px 12px;
  background: #f3f3f3;
  border-bottom: 1px solid #e5e5e5;
}
.email-dot {
  width: 10px; height: 10px; border-radius: 50%;
  background: #ddd;
}
.email-dot:nth-child(1) { background: #ff5f57; }
.email-dot:nth-child(2) { background: #febc2e; }
.email-dot:nth-child(3) { background: #28c840; }
.email-body {
  padding: 16px 18px;
  line-height: 1.7;
}
.flag {
  padding: 1px 4px;
  border-radius: 4px;
  transition: all 0.4s ease;
}
.flag--on {
  background: rgba(239, 68, 68, 0.15);
  color: #dc2626;
  font-weight: 600;
  box-shadow: 0 0 0 1px rgba(239,68,68,0.3);
}
.tag {
  position: absolute;
  right: -64px;
  white-space: nowrap;
  background: #dc2626;
  color: white;
  font-size: 0.7rem;
  padding: 3px 10px;
  border-radius: 20px;
  box-shadow: 0 4px 10px rgba(220,38,38,0.4);
  animation: pop 0.35s ease;
}
.tag-1 { top: 74px; }
.tag-2 { top: 122px; }
.tag-3 { top: 170px; }
@keyframes pop {
  from { transform: scale(0); opacity: 0; }
  to { transform: scale(1); opacity: 1; }
}
</style>